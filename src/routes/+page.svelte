<script lang="ts">
  import Navbar from "$lib/components/Navbar.svelte";
  import Hero from "$lib/components/Hero.svelte";
  import Logos from "$lib/components/Logos.svelte";
  import Features from "$lib/components/Features.svelte";
  import AISection from "$lib/components/AISection.svelte";
  import Direction from "$lib/components/Direction.svelte";
  import Projects from "$lib/components/Projects.svelte";
  import Specs from "$lib/components/Specs.svelte";
  import Issues from "$lib/components/Issues.svelte";
  import CyclesTriage from "$lib/components/CyclesTriage.svelte";
  import Insights from "$lib/components/Insights.svelte";
  import Collaborate from "$lib/components/Collaborate.svelte";
  import Infrastructure from "$lib/components/Infrastructure.svelte";
  import Footer from "$lib/components/Footer.svelte";
</script>

<div class="bg-black min-h-screen text-white selection:bg-purple-500/30 relative">
  <!-- Global Background Effects -->
  <div class="fixed inset-0 bg-[url('https://grainy-gradients.vercel.app/noise.svg')] opacity-20 pointer-events-none z-0 mix-blend-overlay"></div>
  
  <div class="relative z-10">
      <Navbar />
      
      <main>
        <Hero />
    <Logos />
    <Features />
    <AISection />
    <Direction />
    <Projects />
    <Specs />
    <Issues />
    <CyclesTriage />
    <Insights />
    <Collaborate />
    <Infrastructure />
  </main>

  <Footer />
  </div>
</div>

