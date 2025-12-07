<section class="relative pt-32 pb-20 overflow-hidden">
  <!-- Background Glow -->
  <div class="absolute top-0 left-1/2 -translate-x-1/2 w-[1000px] h-[500px] bg-purple-900/20 blur-[120px] rounded-full pointer-events-none -z-10"></div>

  <div class="max-w-[1200px] mx-auto px-6 text-center">
    <h1 class="text-5xl md:text-7xl font-medium tracking-tight mb-6 text-transparent bg-clip-text bg-gradient-to-b from-white to-white/70">
      Linear is a purpose-built tool for<br />planning and building products
    </h1>
    
    <p class="text-xl text-gray-400 mb-10 max-w-2xl mx-auto leading-relaxed">
      Meet the system for modern software development.<br />
      Streamline issues, projects, and product roadmaps.
    </p>
    
    <div class="flex items-center justify-center gap-6 mb-20">
      <button class="bg-white text-black px-6 py-3 rounded-full font-medium hover:bg-gray-100 transition-colors text-sm">
        Start building
      </button>
      <a href="#" class="flex items-center gap-2 text-gray-400 hover:text-white transition-colors text-sm group">
        <span class="text-purple-400">New:</span> Linear agent for Slack
        <svg viewBox="0 0 16 16" class="w-4 h-4 group-hover:translate-x-0.5 transition-transform fill-current">
          <path d="M6.22 3.22a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.75.75 0 0 1-1.06-1.06L9.94 8 6.22 4.28a.75.75 0 0 1 0-1.06Z"/>
        </svg>
      </a>
    </div>

    <!-- Hero Image / Interface Mockup -->
    <div class="relative mx-auto max-w-[1100px] perspective-[2000px]">
      <div class="relative bg-[#0e1012] border border-white/10 rounded-xl shadow-2xl overflow-hidden transform rotate-x-12 scale-95 opacity-90 transition-all duration-1000 hover:scale-100 hover:rotate-x-0 hover:opacity-100 group">
        <!-- Mockup Header -->
        <div class="h-10 border-b border-white/5 bg-white/5 flex items-center px-4 gap-2">
            <div class="flex gap-1.5">
                <div class="w-3 h-3 rounded-full bg-red-500/20"></div>
                <div class="w-3 h-3 rounded-full bg-yellow-500/20"></div>
                <div class="w-3 h-3 rounded-full bg-green-500/20"></div>
            </div>
        </div>
        
        <!-- Mockup Content -->
        <div class="flex h-[600px] text-left">
            <!-- Sidebar -->
            <div class="w-60 border-r border-white/5 p-4 hidden md:block">
                <div class="flex items-center gap-2 mb-6 text-sm font-medium">
                    <div class="w-5 h-5 bg-purple-500 rounded-md"></div>
                    Linear
                </div>
                <div class="space-y-1">
                    <div class="px-2 py-1 bg-white/5 rounded text-sm text-white">Inbox</div>
                    <div class="px-2 py-1 text-sm text-gray-500">My Issues</div>
                </div>
                <div class="mt-6 text-xs font-medium text-gray-500 uppercase tracking-wider mb-2">Workspace</div>
                <div class="space-y-1">
                    <div class="px-2 py-1 text-sm text-gray-400">Initiatives</div>
                    <div class="px-2 py-1 text-sm text-gray-400">Projects</div>
                    <div class="px-2 py-1 text-sm text-gray-400">Views</div>
                    <div class="px-2 py-1 text-sm text-gray-400">Teams</div>
                </div>
            </div>
            
            <!-- Main Content -->
            <div class="flex-1 bg-[#0b0d0e] p-8">
                <div class="flex items-center justify-between mb-8">
                    <div class="flex items-center gap-3">
                        <span class="text-gray-500">ENG-1235</span>
                        <span class="text-gray-400">Refactor sonic crawler</span>
                    </div>
                </div>
                
                <!-- Issue List Mockup -->
                <div class="space-y-2">
                    {#each [1, 2, 3, 4, 5] as i}
                    <div class="flex items-center gap-4 p-3 border border-white/5 rounded bg-white/[0.02] hover:bg-white/[0.04]">
                        <div class="w-4 h-4 border border-gray-600 rounded-full"></div>
                        <div class="flex-1">
                            <div class="h-2 w-48 bg-gray-700 rounded mb-1"></div>
                            <div class="h-1.5 w-32 bg-gray-800 rounded"></div>
                        </div>
                        <div class="w-6 h-6 rounded-full bg-gray-700"></div>
                    </div>
                    {/each}
                </div>
            </div>
        </div>
        
        <!-- Overlay Gradient -->
        <div class="absolute inset-0 bg-gradient-to-t from-[#0b0d0e] via-transparent to-transparent pointer-events-none"></div>
      </div>
    </div>
  </div>
</section>

<style>
    .perspective-\[2000px\] {
        perspective: 2000px;
    }
    .rotate-x-12 {
        transform: rotateX(20deg) scale(0.9);
    }
    .rotate-x-0 {
        transform: rotateX(0deg) scale(1);
    }
</style>
