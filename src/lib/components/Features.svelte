<section class="py-32">
  <div class="max-w-[1200px] mx-auto px-6">
    <div class="mb-20">
      <h2 class="text-4xl md:text-5xl font-medium mb-6">Built for speed,<br />designed for founders</h2>
      <div class="flex flex-col md:flex-row justify-between items-start gap-8">
        <div class="max-w-xl">
             <!-- Spacer -->
        </div>
        <p class="text-xl text-gray-400 max-w-md leading-relaxed">
          Envel eliminates the traditional 3-6 month development cycle through specialized rapid prototyping expertise, letting you validate ideas and secure funding faster. <a href="#" class="text-primary-400 hover:text-primary-300 transition-colors">Start your project ></a>
        </p>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Card 1 -->
      <div class="group relative bg-white/[0.02] border border-white/5 rounded-xl overflow-hidden hover:bg-white/[0.04] transition-colors h-[400px]">
        <div class="absolute inset-0 flex items-center justify-center">
            <!-- Abstract Layers Visualization -->
            <div class="relative w-40 h-40">
                <div class="absolute inset-0 bg-primary-500/20 rounded-lg transform rotate-6 scale-90 translate-x-4 translate-y-4 border border-primary-500/30"></div>
                <div class="absolute inset-0 bg-secondary-500/20 rounded-lg transform -rotate-6 scale-95 -translate-x-2 -translate-y-2 border border-secondary-500/30"></div>
                <div class="absolute inset-0 bg-white/5 backdrop-blur-md rounded-lg border border-white/10 shadow-xl flex items-center justify-center">
                    <div class="w-12 h-12 rounded-full bg-gradient-to-br from-primary-500 to-secondary-500 opacity-50"></div>
                </div>
            </div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 p-8 bg-gradient-to-t from-black/80 to-transparent">
          <h3 class="text-xl font-medium mb-2">Streamlined<br/>workflows</h3>
          <div class="absolute bottom-8 right-8 opacity-0 group-hover:opacity-100 transition-opacity">
            <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center">
                <span class="text-lg">+</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Card 2 -->
      <div class="group relative bg-white/[0.02] border border-white/5 rounded-xl overflow-hidden hover:bg-white/[0.04] transition-colors h-[400px]">
        <div class="absolute inset-0 flex items-center justify-center overflow-hidden">
            <!-- Speed Lines Visualization -->
            <div class="w-full h-full relative">
                {#each [1,2,3,4,5] as i}
                    <div class="absolute h-[1px] bg-gradient-to-r from-transparent via-white/20 to-transparent w-full" style="top: {20 + i * 15}%; left: {-20 + i * 5}%; transform: rotate(-15deg);"></div>
                {/each}
                <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-xs font-mono text-gray-500 bg-black/50 px-2 py-1 rounded border border-white/10">7 days</div>
            </div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 p-8 bg-gradient-to-t from-black/80 to-transparent">
          <h3 class="text-xl font-medium mb-2">Lightning-fast delivery</h3>
          <div class="absolute bottom-8 right-8 opacity-0 group-hover:opacity-100 transition-opacity">
            <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center">
                <span class="text-lg">+</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Card 3 -->
      <div class="group relative bg-white/[0.02] border border-white/5 rounded-xl overflow-hidden hover:bg-white/[0.04] transition-colors h-[400px]">
        <div class="absolute inset-0 flex items-center justify-center">
             <!-- Precision Visualization -->
             <div class="relative">
                <div class="w-32 h-1 bg-white/20 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"></div>
                <div class="w-1 h-32 bg-white/20 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"></div>
                <div class="w-4 h-4 border border-primary-500 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"></div>
                <div class="absolute top-1/2 left-1/2 translate-x-4 translate-y-4 text-[10px] font-mono text-primary-400">Launch</div>
             </div>
        </div>
        <div class="absolute bottom-0 left-0 right-0 p-8 bg-gradient-to-t from-black/80 to-transparent">
          <h3 class="text-xl font-medium mb-2">Production-ready quality</h3>
          <div class="absolute bottom-8 right-8 opacity-0 group-hover:opacity-100 transition-opacity">
            <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center">
                <span class="text-lg">+</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
