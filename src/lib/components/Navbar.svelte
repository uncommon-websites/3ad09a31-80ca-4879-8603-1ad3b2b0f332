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
        <svg width="24" height="23" viewBox="0 0 97 93" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-5 h-5">
          <path d="M57.1677 72.0913C49.5314 69.2599 41.6772 68.8244 34.4772 70.7844C29.459 72.0913 24.6592 74.7049 20.2956 77.9719L17.2411 80.5855L16.3684 81.4566L18.332 83.1991C18.5502 83.1991 18.5502 83.4169 18.7684 83.6347C19.2047 84.0702 19.6411 84.288 20.2956 84.7236L21.6047 85.5947L22.9137 84.5058C23.1319 84.288 23.5683 83.8524 24.0046 83.6347C27.9319 80.3677 32.2953 78.1897 36.8772 77.1008C42.768 75.576 49.0951 75.7938 55.4222 78.1897C60.6585 80.1499 71.3493 82.5455 84.2217 77.1008L84.6581 76.8827L85.3128 76.2294C85.3128 76.0116 85.5309 76.0116 85.7491 75.7938C86.8399 74.4871 87.9309 73.1802 88.8036 71.6557L93.167 64.9038L86.1854 68.8241C75.9309 74.4869 66.5493 75.576 57.1677 72.0913Z" fill="currentColor"/>
          <path d="M27.2782 48.5694C33.169 47.0449 39.4961 47.2627 45.8235 49.6585C52.8051 52.2721 70.6957 55.9746 90.7681 37.8974L95.1317 33.5413L94.6952 32.4524C94.477 31.5812 94.0407 30.4921 93.6044 29.4032L92.5136 26.354L90.3317 28.5318C90.1136 28.9676 89.6773 29.1854 89.2407 29.621C79.641 39.4218 64.8049 49.4407 47.7869 43.3424C40.1509 40.511 32.2964 40.0752 25.0964 42.0355C18.1148 43.9957 12.0058 47.6982 6.33317 52.9255V52.7077L3.0605 56.1924C3.0605 56.4102 2.84236 56.4102 2.62418 56.628L1.9696 57.2813L2.1878 58.1527C2.40597 59.2416 2.84232 60.3305 3.0605 61.4197L4.36959 64.9044L6.55135 62.073C6.76954 61.6374 7.20588 61.4197 7.42407 60.9841C12.0058 56.8458 18.333 50.9652 27.2782 48.5694Z" fill="currentColor"/>
          <path d="M6.11498 44.6486C11.1331 39.4214 16.8057 36.1544 22.9147 34.4119C28.8055 32.8874 35.1327 33.1052 41.4598 35.5011C61.0959 42.6883 78.1138 30.9272 85.5317 24.611L88.368 21.7796L89.4591 20.9085L88.5862 19.6016C87.9317 18.9482 87.4954 18.0771 86.8409 17.2057L85.5317 15.4635L84.0046 16.988C83.7864 17.2058 83.3501 17.6413 83.1317 17.8593C73.9683 26.5713 59.7867 35.5011 43.6416 29.4027C36.0053 26.5713 28.1511 26.1355 20.9511 28.0958C16.3693 29.4027 12.0058 31.5805 7.6422 34.4119L3.06044 38.1147C2.62409 38.5502 2.40591 38.768 1.96955 39.2036L1.53324 39.6391V40.2925C1.31506 41.8172 1.31503 43.3417 1.09685 44.6486L0.878662 50.0936L4.58772 46.1731C5.02406 45.7375 5.46045 45.0841 6.11498 44.6486Z" fill="currentColor"/>
        </svg>
        Envel
      </a>
      
      <div class="hidden md:flex items-center gap-6 text-sm text-gray-400">
        <a href="#process" class="hover:text-white transition-colors">Process</a>
        <a href="#work" class="hover:text-white transition-colors">Work</a>
        <a href="#pricing" class="hover:text-white transition-colors">Pricing</a>
        <a href="#about" class="hover:text-white transition-colors">About</a>
      </div>
    </div>

    <div class="flex items-center gap-4 text-sm">
      <a href="#contact" class="bg-white text-black px-4 py-2 rounded-full font-medium hover:bg-gray-100 transition-colors text-sm">
        Start your project
      </a>
    </div>
  </div>
</nav>
