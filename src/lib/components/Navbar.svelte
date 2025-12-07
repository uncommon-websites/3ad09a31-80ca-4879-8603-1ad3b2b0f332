<script>
  import { onMount } from 'svelte';
  
  let scrolled = false;
  
  onMount(() => {
    const handleScroll = () => {
      scrolled = window.scrollY > 20;
    };
    
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 border-b {scrolled ? 'border-white/5 bg-black/50 backdrop-blur-md' : 'border-transparent bg-transparent'}">
  <div class="max-w-[1200px] mx-auto px-6 h-16 flex items-center justify-between">
    <div class="flex items-center gap-8">
      <a href="/" class="flex items-center gap-2 text-white font-medium hover:opacity-80 transition-opacity">
        <svg viewBox="0 0 24 24" class="w-5 h-5 fill-current" aria-label="Linear Logo">
          <path d="M12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm0 18c-4.418 0-8-3.582-8-8s3.582-8 8-8 8 3.582 8 8-3.582 8-8 8z"/>
          <path d="M12 6a1 1 0 00-1 1v4.26L8.6 12.7a1 1 0 001.4 1.4l2.8-1.68A1 1 0 0013 11.5V7a1 1 0 00-1-1z" class="hidden"/> 
          <!-- Actual Linear logo is simpler, just a shape. I'll use a circle for now or try to match the icon better if I can recall. 
               Linear logo is a stylized 'L' or shapes. Actually it's often just the word 'Linear' or a geometric shape. 
               In the screenshot, it's a small icon. Let's use a simple geometric placeholder. -->
          <circle cx="12" cy="12" r="6" fill="currentColor" />
        </svg>
        Linear
      </a>
      
      <div class="hidden md:flex items-center gap-6 text-sm text-gray-400">
        <a href="#" class="hover:text-white transition-colors">Product</a>
        <a href="#" class="hover:text-white transition-colors">Method</a>
        <a href="#" class="hover:text-white transition-colors">Pricing</a>
        <a href="#" class="hover:text-white transition-colors">Customers</a>
        <a href="#" class="hover:text-white transition-colors">How</a>
        <a href="#" class="hover:text-white transition-colors">Contact</a>
      </div>
    </div>

    <div class="flex items-center gap-4 text-sm">
      <a href="#" class="text-gray-400 hover:text-white transition-colors">Log in</a>
      <a href="#" class="bg-white/10 hover:bg-white/20 text-white px-3 py-1.5 rounded-full border border-white/5 transition-all text-xs font-medium">Sign up</a>
    </div>
  </div>
</nav>
