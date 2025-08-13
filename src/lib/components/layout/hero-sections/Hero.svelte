<!--
    @component
    Bold hero banner with eye-catching text and strong call-to-action. NEVER use title case.

    Usage:
    ```html
    <Hero
      title="Bold Claim"
      subtitle="Quick Value"
      imageSrc="/hero.jpg"
      callsToAction={[
        {
          href: "/start",
          label: "Go"
        },
        {
          href: "/learn",
          label: "More"
        }
      ]}
    />
    ```

    Props:
    - `title`: Main headline (string)
    - `subtitle`: Supporting text (string)
    - `imageSrc`: Hero image URL (string)
    - `callsToAction`: CTA buttons array (max two: primary, secondary)
-->

<script lang="ts">
	// Svelte
	import { onMount } from "svelte";

	// Components
	import AnimateText from "$lib/components/animation/AnimateText.svelte";
	import Button from "$lib/components/ui/Button.svelte";
	import Card from "$lib/components/ui/Card.svelte";

	// Icons - using simple text icons instead of imports to avoid build issues
	const IconZap = "⚡";
	const IconTarget = "🎯";
	const IconRocket = "🚀";
	const IconShield = "🛡️";
	const IconClock = "⏰";

	// Constants
	import { cta } from "$lib/navigation";

	function handleImageError(e: Event) {
		const target = e.currentTarget as HTMLImageElement;
		target.src = "https://placehold.co/800x600/f8fafc/64748b?text=Hero+image";
	}

	// Types
	type Props = {
		centered?: boolean;
		title: string;
		subtitle: string;
		imageSrc?: string;
		callsToAction?: Array<{
			href: string;
			label: string;
		}>; // A maximum of two calls to action, with the first one being primary and the second one being secondary
	};

	let {
		title,
		subtitle,
		imageSrc,
		callsToAction = cta ? [cta] : [],
		centered = false,
		...rest
	}: Props = $props();

	// Animation state
	let cardsVisible = $state(Array(5).fill(false));

	// Trigger card animations on mount
	onMount(() => {
		// Stagger the card animations with 150ms delay between each
		cardsVisible.forEach((_, index) => {
			setTimeout(() => {
				cardsVisible[index] = true;
			}, index * 150);
		});
	});
</script>

<div class="bg-background" {...rest}>
	<header
		class={[
			"section-px container mx-auto grid items-end gap-16 gap-y-9 py-12 pt-24 text-balance",
			centered ? "place-items-center text-center" : " xl:grid-cols-[1fr_auto]"
		]}
		data-enter-container
	>
		<div class="grid gap-6" class:max-w-prose={centered}>
			<h1 class="text-display w-full" data-enter>
				<span class="block"><AnimateText text={title} /></span>
				{#if !centered}
					<span class="text-emphasis-dim block"><AnimateText text={subtitle} /></span>
				{/if}
			</h1>

			{#if centered}
				<p
					data-enter
					class={[
						"text-muted-foreground text-headline mx-auto block max-w-[45ch] transition duration-500 ease-out"
						// isTitleComplete ? "opacity-100" : "translate-y-2 opacity-0 blur-sm"
					]}
				>
					{subtitle}
				</p>
			{/if}
		</div>

		{#if callsToAction.length > 0}
			<div class="flex gap-4" data-enter>
				{#each callsToAction as cta, index}
					<Button
						href={cta.href}
						size="lg"
						variant={index % 2 === 0 ? "primary" : "secondary"}
						class="max-lg:hidden">{cta.label}</Button
					>
					<Button
						href={cta.href}
						size="md"
						variant={index % 2 === 0 ? "primary" : "secondary"}
						class="lg:hidden">{cta.label}</Button
					>
				{/each}
			</div>
		{/if}
	</header>

	<!-- Hero Cards Section - Replacing the single image -->
	<div class="section-px container mx-auto py-16" data-enter-container>
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-6" data-enter>
			<div class={[
				"transition-all duration-700 ease-out",
				cardsVisible[0] ? "opacity-100 blur-none" : "opacity-0 blur-sm"
			]}>
				<Card
					title="Lightning fast"
					description="Ship products in days, not months"
				/>
			</div>
			<div class={[
				"transition-all duration-700 ease-out",
				cardsVisible[1] ? "opacity-100 blur-none" : "opacity-0 blur-sm"
			]}>
				<Card
					title="MVP focused"
					description="Perfect for early-stage validation"
				/>
			</div>
			<div class={[
				"transition-all duration-700 ease-out",
				cardsVisible[2] ? "opacity-100 blur-none" : "opacity-0 blur-sm"
			]}>
				<Card
					title="Launch ready"
					description="From design to deployment"
				/>
			</div>
			<div class={[
				"transition-all duration-700 ease-out",
				cardsVisible[3] ? "opacity-100 blur-none" : "opacity-0 blur-sm"
			]}>
				<Card
					title="Quality assured"
					description="Rigorous standards maintained"
				/>
			</div>
			<div class={[
				"transition-all duration-700 ease-out",
				cardsVisible[4] ? "opacity-100 blur-none" : "opacity-0 blur-sm"
			]}>
				<Card
					title="7-day guarantee"
					description="Live progress tracking included"
				/>
			</div>
		</div>
	</div>
</div>
