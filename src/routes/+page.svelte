<script lang="ts">
	// Components
	import Button from "$lib/components/ui/Button.svelte";
</script>

<div class="min-h-screen bg-background">
	<div class="container mx-auto section-px py-24">
		<div class="max-w-2xl mx-auto text-center space-y-12">
			<!-- One to two sentences at the top -->
			<h1 class="text-display text-balance">
				From idea to product. Fast.
			</h1>
			
			<!-- Short body text explaining what we do -->
			<p class="text-headline text-muted-foreground max-w-prose mx-auto">
				Envel designs, implements, and ships early-stage products rapidly. We help startups transform ideas into market-ready solutions in days, not months.
			</p>
			
			<!-- Contact button -->
			<div class="pt-4">
				<Button 
					href="mailto:hello@nilseller.com"
					size="lg"
					variant="primary"
				>
					Contact us
				</Button>
			</div>
		</div>
	</div>
</div>
