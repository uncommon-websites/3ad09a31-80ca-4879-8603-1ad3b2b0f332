<script lang="ts">
	// Types
	type Testimonial = {
		name?: string;
		author?: string;
		position?: string;
		role?: string;
		company?: string;
		quote: string;
		image?: string; // a 9/16 portrait image of a person
		imageSrc?: string;
	};

	// Props
	let { testimonials, ...rest }: { testimonials: Testimonial[] } = $props();

	// State
	let current = $state(0);
	let scrollProgress = $state(0);
	let wrapperRef: HTMLElement;
	let carouselRef: HTMLElement;
	let maxScrollDistance = $state(0);
	let isTransitioning = $state(false);
	let autoPlayInterval: number | null = null;
	let isPaused = $state(false);

	import { onMount } from "svelte";

	onMount(() => {
		// Keyboard navigation
		const handleKeydown = (event: KeyboardEvent) => {
			if (isTransitioning) return;
			
			switch (event.key) {
				case 'ArrowLeft':
					event.preventDefault();
					prevSlide();
					break;
				case 'ArrowRight':
					event.preventDefault();
					nextSlide();
					break;
				case 'Home':
					event.preventDefault();
					goToSlide(0);
					break;
				case 'End':
					event.preventDefault();
					goToSlide(testimonials.length - 1);
					break;
			}
		};

		window.addEventListener('keydown', handleKeydown);

		// Start auto-play
		startAutoPlay();

		// Preload images
		testimonials.forEach((testimonial) => {
			const imageSrc = testimonial.image || testimonial.imageSrc;
			if (imageSrc) {
				const img = new Image();
				img.loading = "lazy";
				img.src = imageSrc;
			}
		});

		// Calculate the max scroll distance for translation
		const updateDimensions = () => {
			if (!carouselRef) return;

			// Get all cards and container measurements
			const cards = Array.from(carouselRef.querySelectorAll("article"));
			if (!cards.length) return;

			// Get the total width of all content including gaps
			const carouselWidth = carouselRef.scrollWidth;
			// Get the viewport width
			const viewportWidth = window.innerWidth;
			// Get the width of the last card
			const lastCard = cards[cards.length - 1];
			const lastCardWidth = lastCard.offsetWidth;

			// Get computed styles to account for gaps and padding
			const style = getComputedStyle(carouselRef);
			const gapStr = style.gap || style.columnGap || "0px";
			const gapValue = parseInt(gapStr, 10) || 0;

			// To ensure the last card is fully visible at the end of the scroll,
			// we need to make sure the last card's right edge aligns with the viewport's right edge
			// This means the maximum distance we need to translate is:
			// (total carousel width - viewport width)
			// If this value is negative or zero, no scrolling is needed
			maxScrollDistance = Math.max(0, carouselWidth - viewportWidth);

			// Ensure we can see the last card fully
			// This extra adjustment ensures the last card is properly positioned at the end of the scroll
			if (maxScrollDistance > 0) {
				// Add a larger buffer for more breathing room at the right edge
				// This accounts for any padding or margin that might affect positioning
				const buffer = 0; // 4rem buffer instead of 1rem
				maxScrollDistance += buffer;
			}

			if (maxScrollDistance <= 0) {
				console.info("Content fits in viewport, no scrolling needed");
			}
		};

		// Track vertical scroll position and convert to horizontal scroll
		let ticking = false;
		const handleScroll = () => {
			if (ticking) return;
			ticking = true;

			requestAnimationFrame(() => {
				if (!wrapperRef) return;

				const rect = wrapperRef.getBoundingClientRect();
				const sectionHeight = rect.height;
				const viewportHeight = window.innerHeight;

				// Calculate progress (0-1)
				let progress = 0;
				if (rect.top <= 0) {
					progress = Math.min(Math.abs(rect.top) / (sectionHeight - viewportHeight), 1);
				}

				scrollProgress = progress;
				current = Math.min(Math.floor(progress * testimonials.length), testimonials.length - 1);
				ticking = false;
			});
		};

		// Debounce resize handler for better performance
		let resizeTimer: number;
		const handleResize = () => {
			clearTimeout(resizeTimer);
			resizeTimer = setTimeout(() => {
				updateDimensions();
				handleScroll();
			}, 100);
		};

		// Initialize and set up listeners
		updateDimensions();
		window.addEventListener("resize", handleResize);
		window.addEventListener("scroll", handleScroll);
		setTimeout(() => {
			updateDimensions(); // Run once more after DOM is settled
			handleScroll();
		}, 100);

		return () => {
			window.removeEventListener("resize", handleResize);
			window.removeEventListener("scroll", handleScroll);
			window.removeEventListener('keydown', handleKeydown);
			stopAutoPlay();
			clearTimeout(resizeTimer);
		};
	});

	// Navigation functions
	function goToSlide(index: number) {
		if (isTransitioning || index === current) return;
		
		isTransitioning = true;
		current = index;
		scrollProgress = index / (testimonials.length - 1);
		
		// Reset transition flag after animation
		setTimeout(() => {
			isTransitioning = false;
		}, 300);
	}

	function nextSlide() {
		const nextIndex = current < testimonials.length - 1 ? current + 1 : 0;
		goToSlide(nextIndex);
	}

	function prevSlide() {
		const prevIndex = current > 0 ? current - 1 : testimonials.length - 1;
		goToSlide(prevIndex);
	}

	// Auto-play functionality
	function startAutoPlay() {
		if (autoPlayInterval) clearInterval(autoPlayInterval);
		autoPlayInterval = setInterval(() => {
			if (!isPaused && !isTransitioning) {
				nextSlide();
			}
		}, 5000); // 5 seconds
	}

	function stopAutoPlay() {
		if (autoPlayInterval) {
			clearInterval(autoPlayInterval);
			autoPlayInterval = null;
		}
	}

	function pauseAutoPlay() {
		isPaused = true;
	}

	function resumeAutoPlay() {
		isPaused = false;
	}
</script>

<section
	bind:this={wrapperRef}
	class="text-pretty [--gap:--spacing(4)]"
	style="height: calc(100vh * {testimonials.length});"
	role="region"
	aria-label="Customer testimonials carousel"
	aria-live="polite"
	{...rest}
>
	<div
		class="section-py section-px sticky top-0 flex min-h-screen w-full items-center overflow-hidden"
		onmouseenter={pauseAutoPlay}
		onmouseleave={resumeAutoPlay}
		onfocusin={pauseAutoPlay}
		onfocusout={resumeAutoPlay}
	>
		<div
			bind:this={carouselRef}
			class={[
				"flex w-full gap-(--card-gap) pr-8 [--card-gap:--spacing(6)]",
				"[--inner-radius:calc(var(--outer-radius)-var(--gap))] [--outer-radius:var(--radius)] lg:[--outer-radius:var(--radius-xl)]"
			]}
			role="group"
			aria-label="Testimonials"
		>
			{#each testimonials as testimonial, index}
				<article
					role="tabpanel"
					aria-label="Testimonial {index + 1} of {testimonials.length}"
					class={[
						"lg:container-xs  lg:min-w-[50%] lg:grid-cols-[2fr_3fr]",
						"items-between grid grid-cols-1 gap-8",
						"bg-card dark:text-white",
						"aspect-video max-w-full min-w-full xl:aspect-[auto]",
						"transform-gpu will-change-transform",
						"rounded-(--outer-radius) p-(--gap)",
						"border-border border contain-layout",
						isTransitioning ? "transition-transform duration-500 ease-[cubic-bezier(0.16,1,0.3,1)]" : "transition-transform duration-200 ease-[cubic-bezier(0.16,1,0.3,1)]"
					]}
					style:transform="translateX(calc(-{scrollProgress} * {maxScrollDistance}px))"
				>
					<div class="hidden overflow-clip rounded-[max(var(--inner-radius),2px)] lg:block">
						{#if testimonial.image || testimonial.imageSrc}
							<img
								src={testimonial.image || testimonial.imageSrc}
								alt="{testimonial.name || testimonial.author} testimonial"
								loading="lazy"
								class="aspect-[3/4] h-full w-full object-cover"
							/>
						{/if}
					</div>
					<div class="flex flex-col justify-between gap-12">
						<q class="text-title2 max-w-prose">{testimonial.quote}</q>
						<cite class="text-caption flex items-center gap-3 not-italic">
							{#if testimonial.image || testimonial.imageSrc}
								<img
									src={testimonial.image || testimonial.imageSrc}
									alt="{testimonial.name || testimonial.author} testimonial"
									loading="lazy"
									class="size-12 rounded-full object-cover lg:hidden"
								/>
							{/if}
							<div>
								<p class="text-callout">{testimonial.name || testimonial.author}</p>
								<p class="text-muted-foreground">
									{testimonial.position || testimonial.role}{#if testimonial.company}, {testimonial.company}{/if}
								</p>
							</div>
						</cite>
					</div>
				</article>
			{/each}
			<!-- Empty spacer to ensure last card has breathing room -->
			<div class="min-w-(--gap) lg:min-w-[calc(var(--gap)*3)]"></div>
		</div>

		<!-- Navigation Controls -->
		<div class="absolute inset-y-0 left-4 flex items-center">
			<button
				onclick={prevSlide}
				class={[
					"bg-card hover:bg-card-hover border-border",
					"size-12 rounded-full border transition-all duration-200",
					"flex items-center justify-center",
					"focus:outline-none focus:ring-2 focus:ring-primary focus:ring-offset-2",
					"disabled:opacity-50 disabled:cursor-not-allowed"
				]}
				disabled={isTransitioning}
				aria-label="Previous testimonial"
			>
				<svg class="size-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
				</svg>
			</button>
		</div>

		<div class="absolute inset-y-0 right-4 flex items-center">
			<button
				onclick={nextSlide}
				class={[
					"bg-card hover:bg-card-hover border-border",
					"size-12 rounded-full border transition-all duration-200",
					"flex items-center justify-center",
					"focus:outline-none focus:ring-2 focus:ring-primary focus:ring-offset-2",
					"disabled:opacity-50 disabled:cursor-not-allowed"
				]}
				disabled={isTransitioning}
				aria-label="Next testimonial"
			>
				<svg class="size-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
				</svg>
			</button>
		</div>

		<!-- Pagination Indicators -->
		<div class="absolute bottom-8 left-1/2 flex -translate-x-1/2 justify-center gap-2">
			{#each testimonials as _, index}
				<button
					onclick={() => goToSlide(index)}
					class={[
						"bg-emphasis-dim size-1.5 rounded-full transition-all duration-300 ease-in-out",
						"focus:outline-none focus:ring-2 focus:ring-primary focus:ring-offset-2",
						"hover:opacity-80",
						current === index ? "w-8 opacity-100" : "opacity-50"
					]}
					disabled={isTransitioning}
					aria-label="Go to testimonial {index + 1}"
				></button>
			{/each}
		</div>
	</div>
</section>

<style>
	/* Hide scrollbar while preserving functionality */
	.hide-scrollbar {
		-ms-overflow-style: none;
		scrollbar-width: none;
	}
	.hide-scrollbar::-webkit-scrollbar {
		display: none;
	}
</style>
