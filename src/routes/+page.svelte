<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import Hero from "$lib/components/layout/hero-sections/Hero.svelte";
</script>

<Hero
	title="From idea to product. Fast."
	subtitle="We help early-stage teams design, build, and ship real products in days—not months."
	imageSrc="/generated/image-a-clean-minimal-workspace-featuring-a-la.webp"
	callsToAction={[
		{
			href: "/contact",
			label: "Join waitlist"
		},
		{
			href: "/about",
			label: "Learn more"
		}
	]}
/>
<LogoScroller 
	label="Trusted by innovative companies" 
	logoUrls={[
		'https://cdn.brandfetch.io/canva.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7',
		'https://cdn.brandfetch.io/notion.so/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7',
		'https://cdn.brandfetch.io/stripe.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7',
		'https://cdn.brandfetch.io/figma.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7'
	]} 
/>

<Summary
	title="What we do"
	text="Envel designs, implements, and ships early-stage products rapidly, transforming your ideas into market-ready solutions. We specialize in accelerating product development from months to days for startups and innovators. Our comprehensive approach covers everything from design to deployment, helping you validate concepts and reach market faster."
/>

<Testimonials
	testimonials={[
		{
			name: "Keiko Landa",
			position: "Co-founder",
			company: "Arrayloop",
			quote:
				"Envel turned a months-long roadmap into a live product in under a week. Our MVP was built, polished, and in customer hands before some teams finish discovery. That kind of acceleration changed everything for us.",
			image: "/generated/image-a-professional-woman-stands-confidently-.webp"
		},
		{
			name: "Omar Petrov",
			position: "Founder",
			company: "MetricBay",
			quote:
				"With Envel, we were able to go from idea to real-world validation in five days. That speed helped us test assumptions and avoid pouring six months into the wrong direction. It de-risked our startup early—massively.",
			image: "/generated/image-a-professional-man-is-sitting-on-a-downt.webp"
		},
		{
			name: "ClareShawnellis Vega",
			position: "Owner",
			company: "Reclaim Accounting",
			quote:
				"We saved tens of thousands by not hiring a full team. Envel handled everything from product design to deployment—and did it in under a week. What we got would've taken agencies two months and four invoices.",
			image: "/generated/image-a-professional-woman-is-working-in-her-h.webp"
		}
	]}
/>

<Features
	title="Why choose Envel"
	subtitle="Accelerated development that doesn't compromise on quality"
	features={[
		{
			title: "Lightning fast delivery",
			description:
				"Transform your product ideas into shipping-ready solutions in days, not months through our streamlined development process."
		},
		{
			title: "Quality-first approach",
			description:
				"Every product we ship meets rigorous quality standards while maintaining the speed you need to stay competitive."
		},
		{
			title: "End-to-end development",
			description:
				"From initial design concepts to final implementation and deployment, we handle your entire product development lifecycle."
		},
		{
			title: "Early-stage expertise",
			description:
				"Purpose-built for startups and entrepreneurs who need to validate ideas quickly and iterate based on real user feedback."
		},
		{
			title: "Proven methodology",
			description:
				"Our battle-tested process eliminates typical development bottlenecks that slow down traditional agencies and in-house teams."
		},
		{
			title: "Immediate availability",
			description:
				"Join our waitlist to access rapid product development services designed specifically for time-sensitive early-stage ventures."
		}
	]}
/>
<AboutTeaser />
<CallToAction />
