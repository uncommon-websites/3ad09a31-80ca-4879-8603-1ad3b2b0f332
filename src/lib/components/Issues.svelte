<section class="py-24 overflow-hidden">
  <div class="max-w-[1200px] mx-auto px-6 mb-16">
    <div class="flex items-center gap-2 text-primary-500 mb-4 text-sm font-medium">
        <svg viewBox="0 0 16 16" class="w-4 h-4 fill-current">
            <path d="M0 2.5A.5.5 0 0 1 .5 2H2a.5.5 0 0 1 .485.379L2.89 4H14.5a.5.5 0 0 1 .485.621l-1.5 6A.5.5 0 0 1 13 11H4a.5.5 0 0 1-.485-.379L1.61 3H.5a.5.5 0 0 1-.5-.5zM3.14 5l1.25 5h8.22l1.25-5H3.14zM5 13a1 1 0 1 0 0 2 1 1 0 0 0 0-2zm-2 1a2 2 0 1 1 4 0 2 2 0 0 1-4 0zm9-1a1 1 0 1 0 0 2 1 1 0 0 0 0-2zm-2 1a2 2 0 1 1 4 0 2 2 0 0 1-4 0z"/>
        </svg>
        Transparent development process
    </div>
    <h2 class="text-4xl md:text-5xl font-medium mb-6">Real-time progress<br />tracking dashboard</h2>
    <p class="text-xl text-gray-400 max-w-2xl">
      <strong class="text-white">See exactly where your project stands.</strong> Track every feature, milestone, and deliverable with live updates. No surprises, just transparent progress.
    </p>
  </div>

  <!-- Large 3D Interface Mockup -->
  <div class="relative w-full h-[800px] flex items-center justify-center -mt-20">
    <div class="absolute inset-0 bg-gradient-to-b from-transparent via-transparent to-black pointer-events-none z-10"></div>
    
    <div class="perspective-[2000px] w-full max-w-[1400px]">
        <div class="relative transform rotate-x-20 rotate-y-10 rotate-z-[-5deg] scale-90 origin-center translate-y-20">
            <!-- Main Board Layer -->
            <div class="bg-[#0e1012] border border-white/10 rounded-xl shadow-2xl p-6 w-[1200px] h-[800px] relative">
                <!-- Header -->
                <div class="flex items-center gap-8 mb-8 border-b border-white/5 pb-4">
                    <div class="text-white font-medium">High Priority</div>
                    <div class="text-gray-500">No Priority</div>
                    <div class="text-gray-500">Backlog</div>
                </div>

                <!-- Issues List -->
                <div class="space-y-4">
                    <!-- Issue 1 -->
                    <div class="flex items-center gap-4 p-4 bg-white/[0.02] border border-white/5 rounded-lg hover:bg-white/[0.04] transition-colors group">
                        <div class="w-4 h-4 border border-orange-500 rounded-full"></div>
                        <div class="text-gray-500 font-mono text-sm">ENG-1025</div>
                        <div class="text-white font-medium flex-1">Improve keyboard shortcuts</div>
                        <div class="flex items-center gap-2">
                            <span class="px-2 py-1 bg-white/5 rounded text-xs text-gray-400 border border-white/5">UI Refresh</span>
                            <div class="w-6 h-6 rounded-full bg-purple-500"></div>
                        </div>
                    </div>

                    <!-- Issue 2 (Active/Selected) -->
                    <div class="relative transform translate-x-10 -translate-y-2 z-20">
                        <div class="absolute -inset-1 bg-blue-500/20 blur-xl rounded-lg"></div>
                        <div class="flex items-center gap-4 p-6 bg-[#1a1c1e] border border-blue-500/30 rounded-lg shadow-2xl relative">
                            <div class="w-5 h-5 bg-blue-500 rounded-full flex items-center justify-center">
                                <svg viewBox="0 0 12 12" class="w-3 h-3 fill-white"><path d="M3.5 9.5L1 7l1.41-1.41L3.5 6.67l5.09-5.09L10 3z"/></svg>
                            </div>
                            <div class="text-blue-400 font-mono text-sm">ENG-1012</div>
                            <div class="text-white text-lg font-medium flex-1">Update payment gateway integration</div>
                            <div class="flex items-center gap-2">
                                <span class="px-2 py-1 bg-blue-500/10 rounded text-xs text-blue-400 border border-blue-500/20">PSD2 Regulation</span>
                                <div class="w-8 h-8 rounded-full bg-gray-700 border border-white/10"></div>
                            </div>
                        </div>
                    </div>

                    <!-- Issue 3 -->
                    <div class="flex items-center gap-4 p-4 bg-white/[0.02] border border-white/5 rounded-lg hover:bg-white/[0.04] transition-colors opacity-60">
                         <div class="w-4 h-4 border border-gray-600 rounded-full"></div>
                        <div class="text-gray-500 font-mono text-sm">ENG-954</div>
                        <div class="text-gray-400 font-medium flex-1">TimeoutError: Transaction timed out due...</div>
                        <div class="flex items-center gap-2">
                             <span class="px-2 py-1 bg-white/5 rounded text-xs text-gray-500 border border-white/5">Mobile v1</span>
                            <div class="w-6 h-6 rounded-full bg-gray-800"></div>
                        </div>
                    </div>
                    
                     <!-- Issue 4 -->
                    <div class="flex items-center gap-4 p-4 bg-white/[0.02] border border-white/5 rounded-lg hover:bg-white/[0.04] transition-colors opacity-40">
                         <div class="w-4 h-4 border border-gray-600 rounded-full"></div>
                        <div class="text-gray-500 font-mono text-sm">ENG-902</div>
                        <div class="text-gray-400 font-medium flex-1">Remove duplicated Postgres indexes</div>
                        <div class="flex items-center gap-2">
                             <span class="px-2 py-1 bg-white/5 rounded text-xs text-gray-500 border border-white/5">Mobile v1</span>
                            <div class="w-6 h-6 rounded-full bg-gray-800"></div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Floating Elements / Depth Layers -->
            <div class="absolute top-20 right-20 w-64 p-4 bg-[#1a1c1e]/90 backdrop-blur-md border border-white/10 rounded-lg shadow-2xl transform translate-z-20 rotate-y-[-10deg]">
                <div class="text-xs text-gray-500 mb-2">Urgent</div>
                <div class="flex items-center gap-2 mb-1">
                    <span class="text-gray-400 font-mono text-xs">ENG-1018</span>
                    <span class="text-white text-sm">Implement AES-256 Encryption</span>
                </div>
                <div class="flex gap-2 mt-2">
                     <span class="px-1.5 py-0.5 bg-red-500/10 text-red-400 text-[10px] rounded border border-red-500/20">Security improvements</span>
                </div>
            </div>
        </div>
    </div>
  </div>
</section>

<style>
    .rotate-x-20 {
        transform: rotateX(20deg);
    }
    .rotate-y-10 {
        transform: rotateY(10deg);
    }
    .rotate-z-\[-5deg\] {
        transform: rotateZ(-5deg);
    }
    .translate-z-20 {
        transform: translateZ(50px);
    }
</style>
