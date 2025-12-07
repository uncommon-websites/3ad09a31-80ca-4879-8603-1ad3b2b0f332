<section class="py-24 border-t border-white/5">
  <div class="max-w-[1200px] mx-auto px-6">
    <div class="mb-16">
      <h2 class="text-4xl font-medium mb-4">Linear Insights</h2>
      <p class="text-xl text-gray-400 max-w-2xl mb-8">
        Take the guesswork out of product planning with realtime analytics and reporting dashboards.
      </p>
      <button class="bg-white/10 hover:bg-white/20 text-white px-4 py-2 rounded-full text-sm font-medium transition-colors border border-white/5">
        Learn more >
      </button>
    </div>

    <!-- Chart Mockup -->
    <div class="bg-[#0e1012] border border-white/10 rounded-xl p-8 h-[500px] relative overflow-hidden">
        <!-- Chart Header -->
        <div class="flex items-center justify-between mb-8">
             <div class="flex items-center gap-4">
                 <div class="text-white font-medium">Cycle Time</div>
                 <div class="flex items-center gap-2 text-xs text-gray-500">
                     <span class="w-2 h-2 rounded-full bg-blue-500"></span> Segment
                 </div>
                 <div class="flex items-center gap-2 text-xs text-gray-500">
                     <span class="w-2 h-2 rounded-full bg-purple-500"></span> Team
                 </div>
             </div>
             <div class="flex items-center gap-2 text-xs text-gray-500 border border-white/10 rounded px-2 py-1">
                 Last 3 months <svg viewBox="0 0 12 12" class="w-2 h-2 fill-current"><path d="M6 8L3 5h6z"/></svg>
             </div>
        </div>

        <!-- Chart Area -->
        <div class="relative h-[350px] w-full">
            <!-- Y Axis Labels -->
            <div class="absolute left-0 top-0 bottom-0 w-10 flex flex-col justify-between text-[10px] text-gray-600 font-mono py-2">
                <span>7d</span>
                <span>5d</span>
                <span>3d</span>
                <span>1d</span>
                <span>0d</span>
            </div>
            
            <!-- X Axis Labels -->
            <div class="absolute left-10 right-0 bottom-0 h-6 flex justify-between text-[10px] text-gray-600 font-mono px-4">
                <span>Oct 1</span>
                <span>Oct 15</span>
                <span>Nov 1</span>
                <span>Nov 15</span>
                <span>Dec 1</span>
                <span>Dec 15</span>
                <span>Jan 1</span>
                <span>Jan 15</span>
                <span>Feb 1</span>
                <span>Feb 15</span>
            </div>
            
            <!-- Grid -->
            <div class="absolute left-10 right-0 top-0 bottom-6 border-l border-b border-white/5">
                <div class="w-full h-1/4 border-t border-white/5 border-dashed opacity-30"></div>
                <div class="w-full h-1/4 border-t border-white/5 border-dashed opacity-30"></div>
                <div class="w-full h-1/4 border-t border-white/5 border-dashed opacity-30"></div>
                <div class="w-full h-1/4 border-t border-white/5 border-dashed opacity-30"></div>
            </div>
            
            <!-- Scatter Points -->
            <div class="absolute left-10 right-0 top-0 bottom-6 overflow-hidden">
                {#each Array(100) as _, i}
                    <div 
                        class="absolute w-1.5 h-1.5 rounded-full opacity-70"
                        style="
                            left: {Math.random() * 100}%; 
                            top: {Math.random() * 100}%; 
                            background-color: {Math.random() > 0.5 ? '#3b82f6' : '#a855f7'};
                            opacity: {Math.random() * 0.5 + 0.3};
                        "
                    ></div>
                {/each}
                
                <!-- Highlighted Points / Trend -->
                <div class="absolute w-2 h-2 bg-white rounded-full shadow-[0_0_10px_rgba(255,255,255,0.5)]" style="left: 60%; top: 40%;"></div>
                <div class="absolute w-2 h-2 bg-white rounded-full shadow-[0_0_10px_rgba(255,255,255,0.5)]" style="left: 65%; top: 35%;"></div>
                
                <!-- Tooltip Mockup -->
                <div class="absolute left-[62%] top-[25%] bg-[#1a1c1e] border border-white/10 rounded p-2 text-[10px] z-10 shadow-xl">
                    <div class="text-gray-400">ENG-2938</div>
                    <div class="text-white font-medium">API Latency Fix</div>
                    <div class="text-blue-400">3 days</div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- 4 Features Grid Below Chart -->
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mt-12">
        <div>
            <div class="flex items-center gap-2 text-white font-medium mb-2">
                <svg viewBox="0 0 24 24" class="w-4 h-4 text-gray-400 fill-current"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 17h-2v-2h2v2zm2.07-7.75l-.9.92C13.45 12.9 13 13.5 13 15h-2v-.5c0-1.1.45-2.1 1.17-2.83l1.24-1.26c.37-.36.59-.86.59-1.41 0-1.1-.9-2-2-2s-2 .9-2 2H8c0-2.21 1.79-4 4-4s4 1.79 4 4c0 .88-.36 1.68-.93 2.25z"/></svg>
                Tailored workflows
            </div>
            <p class="text-sm text-gray-500 leading-relaxed">Track progress across custom issue flows for your team.</p>
        </div>
        <div>
            <div class="flex items-center gap-2 text-white font-medium mb-2">
                <svg viewBox="0 0 24 24" class="w-4 h-4 text-gray-400 fill-current"><path d="M3 13h2v-2H3v2zm0 4h2v-2H3v2zm0-8h2V7H3v2zm4 4h14v-2H7v2zm0 4h14v-2H7v2zM7 7v2h14V7H7z"/></svg>
                Custom views
            </div>
            <p class="text-sm text-gray-500 leading-relaxed">Switch between list and board. Group issues with swimlanes.</p>
        </div>
        <div>
            <div class="flex items-center gap-2 text-white font-medium mb-2">
                <svg viewBox="0 0 24 24" class="w-4 h-4 text-gray-400 fill-current"><path d="M10 18h4v-2h-4v2zM3 6v2h18V6H3zm3 7h12v-2H6v2z"/></svg>
                Filters
            </div>
            <p class="text-sm text-gray-500 leading-relaxed">Refine issue lists down to what's most relevant to you.</p>
        </div>
        <div>
            <div class="flex items-center gap-2 text-white font-medium mb-2">
                <svg viewBox="0 0 24 24" class="w-4 h-4 text-gray-400 fill-current"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"/></svg>
                SLAs
            </div>
            <p class="text-sm text-gray-500 leading-relaxed">Automatically apply deadlines to time-sensitive tasks.</p>
        </div>
    </div>
  </div>
</section>
