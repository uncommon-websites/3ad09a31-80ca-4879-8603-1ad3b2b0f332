<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Speed",
			description: "Delivering quality products in days, not months, without compromising excellence."
		},
		{
			title: "Quality",
			description: "Every product we ship maintains the highest standards of design and functionality."
		},
		{
			title: "Innovation",
			description: "Revolutionizing product development through streamlined processes and cutting-edge solutions."
		}
	];
</script>

<SecondaryHero
	title="Accelerating innovation"
	subtitle="from months to days"
	imageSrc="/generated/image-a-professional-team-collaborating-in-a-m.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Envel was founded with a revolutionary vision: to transform the traditional product development timeline from months to days. We recognized that early-stage companies were being held back by lengthy development cycles that prevented rapid iteration and market validation.",
		"Our comprehensive approach covers the entire product lifecycle - from initial design and user experience through technical implementation and deployment. We don't just build products; we accelerate dreams into reality with uncompromising quality.",
		"Founded by Nils Eller, Envel operates on the principle that speed shouldn't sacrifice quality. Every product we ship maintains the highest standards while dramatically reducing time to market, giving our clients the competitive edge they need.",
		"We currently operate on a waitlist model, carefully selecting early-stage companies and entrepreneurs who share our vision for rapid innovation. Our mission is simple: help visionaries bring their products to market faster than ever before possible."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Our team."
	subtitle="Accelerating your vision."
	stakeholders={[
		{
			name: "Nils Eller",
			position: "Founder & CEO",
			bio: "Visionary leader dedicated to revolutionizing product development timelines and helping early-stage companies achieve rapid market entry.",
			image: "/generated/image-a-focused-entrepreneur-working-on-produc.webp"
		},
		{
			name: "Product Development Team",
			position: "Design & Engineering",
			bio: "Expert team specializing in rapid prototyping, user experience design, and technical implementation for early-stage products.",
			image: "/generated/image-a-diverse-team-brainstorming-innovative-.webp"
		}
	]}
/>

<StakeholderGrid
	stakeholderType="investor"
	title="Join our waitlist."
	subtitle="Exclusive access to rapid product development"
	stakeholders={[
		{
			name: "Early Access",
			image: "/generated/image-a-focused-entrepreneur-working-on-produc.webp"
		},
		{
			name: "Priority Support",
			image: "/generated/image-a-diverse-team-brainstorming-innovative-.webp"
		},
		{
			name: "Rapid Delivery",
			image: "/generated/image-a-professional-team-collaborating-in-a-m.webp"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
	title="Ready to accelerate your product?"
	subtitle="From concept to market in days"
	description="Join our exclusive waitlist and discover how Envel can transform your product development timeline from months to days while maintaining exceptional quality."
/>
