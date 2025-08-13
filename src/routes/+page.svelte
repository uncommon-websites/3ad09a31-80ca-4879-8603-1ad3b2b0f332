<script lang="ts">
	// Components
	import Button from "$lib/components/ui/Button.svelte";
</script>

<div class="bg-background">
	<div class="container mx-auto section-px py-12">
		<article class="max-w-2xl mx-auto space-y-6">
			<!-- Simple article heading -->
			<h1 class="text-4xl font-semibold text-left leading-tight">
				From idea to product. Fast.
			</h1>
			
			<!-- Article body -->
			<div class="text-left space-y-4">
				<p class="text-lg text-muted-foreground leading-relaxed">
					Envel designs, implements, and ships early-stage products rapidly. We help startups transform ideas into market-ready solutions in days, not months.
				</p>
			</div>
			
			<!-- Simple contact button -->
			<div class="pt-4">
				<Button 
					href="mailto:hello@nilseller.com"
					size="md"
					variant="primary"
				>
					Contact us
				</Button>
			</div>
		</article>
	</div>
</div>
