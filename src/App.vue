<script setup lang="ts">
import { ref } from 'vue'

const activeTab = ref('today')
</script>

<template>
  <div class="min-h-screen bg-black text-white font-sans overflow-hidden">
    <!-- Top Bar -->
    <div class="pt-16 pb-6 px-4">
      <div class="flex items-center justify-between mb-2">
        <div>
          <p class="text-xs font-semibold text-gray-400 uppercase tracking-wider mb-1">
            Monday, August 2
          </p>
          <h1 class="text-3xl font-bold tracking-tight">Today</h1>
        </div>
        <div class="w-9 h-9 bg-blue-500 rounded-full flex items-center justify-center">
          <svg class="w-5 h-5 text-white" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
          </svg>
        </div>
      </div>
    </div>

    <!-- Main Content -->
    <div class="px-4 pb-24">
      <!-- Featured App Card -->
      <div class="relative overflow-hidden rounded-xl shadow-2xl">
        <!-- Hero Image with Rainbow Heart -->
        <div class="relative h-80 bg-gradient-to-br from-purple-500 via-purple-600 to-purple-700">
          <!-- Background Pattern -->
          <div class="absolute inset-0 bg-purple-500">
            <!-- Rainbow Heart -->
            <div class="absolute inset-0 flex items-center justify-center">
              <div class="relative">
                <!-- Heart Shape with Rainbow Stripes -->
                <div class="w-48 h-40 relative">
                  <svg viewBox="0 0 100 85" class="w-full h-full">
                    <defs>
                      <pattern id="rainbow" x="0" y="0" width="100%" height="100%" patternUnits="userSpaceOnUse">
                        <rect x="0" y="0" width="8.33%" height="100%" fill="#8B4513"/>
                        <rect x="8.33%" y="0" width="8.33%" height="100%" fill="#FF69B4"/>
                        <rect x="16.66%" y="0" width="8.33%" height="100%" fill="#FF0000"/>
                        <rect x="25%" y="0" width="8.33%" height="100%" fill="#FF8C00"/>
                        <rect x="33.33%" y="0" width="8.33%" height="100%" fill="#FFD700"/>
                        <rect x="41.66%" y="0" width="8.33%" height="100%" fill="#ADFF2F"/>
                        <rect x="50%" y="0" width="8.33%" height="100%" fill="#00FF00"/>
                        <rect x="58.33%" y="0" width="8.33%" height="100%" fill="#00CED1"/>
                        <rect x="66.66%" y="0" width="8.33%" height="100%" fill="#00BFFF"/>
                        <rect x="75%" y="0" width="8.33%" height="100%" fill="#0000FF"/>
                        <rect x="83.33%" y="0" width="8.33%" height="100%" fill="#8A2BE2"/>
                        <rect x="91.66%" y="0" width="8.34%" height="100%" fill="#4B0082"/>
                      </pattern>
                    </defs>
                    <path d="M50,75 C50,75 20,50 20,30 C20,15 30,5 45,15 C50,20 50,20 55,15 C70,5 80,15 80,30 C80,50 50,75 50,75 Z" 
                          fill="url(#rainbow)" 
                          stroke="#333" 
                          stroke-width="0.5"/>
                  </svg>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Overlay Text -->
          <div class="absolute top-4 left-4 z-10">
            <p class="text-white text-sm font-semibold uppercase tracking-wider opacity-60 mb-1">
              Utilities
            </p>
            <h2 class="text-white text-2xl font-bold tracking-wide">
              Figma
            </h2>
          </div>

          <!-- Corner Decorations -->
          <div class="absolute top-3 left-3 w-8 h-8 border-2 border-white border-r-0 border-b-0 rounded-tl-lg"></div>
          <div class="absolute top-3 right-3 w-8 h-8 border-2 border-white border-l-0 border-b-0 rounded-tr-lg"></div>
          <div class="absolute bottom-3 left-3 w-8 h-8 border-2 border-white border-r-0 border-t-0 rounded-bl-lg"></div>
          <div class="absolute bottom-3 right-3 w-8 h-8 border-2 border-white border-l-0 border-t-0 rounded-br-lg"></div>
          
          <!-- Small decorative squares -->
          <div class="absolute top-8 left-8 w-4 h-3 bg-orange-500 rounded-sm"></div>
          <div class="absolute top-8 right-8 w-4 h-3 bg-yellow-400 rounded-sm"></div>
          <div class="absolute bottom-20 left-8 w-4 h-3 bg-red-500 rounded-sm"></div>
          <div class="absolute bottom-20 right-8 w-4 h-3 bg-blue-500 rounded-sm"></div>
        </div>

        <!-- App Details Section -->
        <div class="bg-gray-800 p-4">
          <div class="flex items-center justify-between">
            <div class="flex items-center space-x-4">
              <!-- App Icon -->
              <div class="w-12 h-12 rounded-xl border border-gray-600 overflow-hidden flex-shrink-0">
                <img 
                  src="https://api.builder.io/api/v1/image/assets/TEMP/53c7d0d79a9655a201ff1c663652323862f47f7c?width=94" 
                  alt="Figma Icon" 
                  class="w-full h-full object-cover"
                />
              </div>
              
              <!-- App Info -->
              <div class="flex-1 min-w-0">
                <p class="text-xs text-gray-400 uppercase tracking-wider font-semibold mb-1">
                  Utilities
                </p>
                <h3 class="text-white text-base font-semibold mb-1">
                  Figma
                </h3>
                <p class="text-gray-400 text-sm">
                  Figma Inc.
                </p>
              </div>
            </div>
            
            <!-- Get Button -->
            <button class="bg-gray-700 hover:bg-gray-600 transition-colors px-6 py-2 rounded-full">
              <span class="text-blue-400 font-bold text-sm tracking-wider">
                GET
              </span>
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom Navigation -->
    <div class="fixed bottom-0 left-0 right-0 bg-black bg-opacity-75 backdrop-blur-lg border-t border-gray-800">
      <div class="flex items-center justify-around py-2">
        <!-- Today Tab -->
        <button 
          class="flex flex-col items-center py-2 px-4"
          :class="activeTab === 'today' ? 'text-blue-400' : 'text-gray-400'"
          @click="activeTab = 'today'"
        >
          <svg class="w-6 h-6 mb-1" fill="currentColor" viewBox="0 0 24 24">
            <path d="M19 3h-1V1h-2v2H8V1H6v2H5c-1.11 0-1.99.9-1.99 2L3 19c0 1.1.89 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 16H5V8h14v11zM7 10h5v5H7z"/>
          </svg>
          <span class="text-xs font-medium">Today</span>
        </button>

        <!-- Games Tab -->
        <button 
          class="flex flex-col items-center py-2 px-4"
          :class="activeTab === 'games' ? 'text-blue-400' : 'text-gray-400'"
          @click="activeTab = 'games'"
        >
          <svg class="w-6 h-6 mb-1" fill="currentColor" viewBox="0 0 24 24">
            <path d="M21,6V8H3V6H21M3,18H12V16H3V18M3,13H21V11H3V13Z"/>
          </svg>
          <span class="text-xs font-medium">Games</span>
        </button>

        <!-- Apps Tab -->
        <button 
          class="flex flex-col items-center py-2 px-4"
          :class="activeTab === 'apps' ? 'text-blue-400' : 'text-gray-400'"
          @click="activeTab = 'apps'"
        >
          <svg class="w-6 h-6 mb-1" fill="currentColor" viewBox="0 0 24 24">
            <path d="M6,8A2,2 0 0,1 4,6A2,2 0 0,1 6,4A2,2 0 0,1 8,6A2,2 0 0,1 6,8M6,20A2,2 0 0,1 4,18A2,2 0 0,1 6,16A2,2 0 0,1 8,18A2,2 0 0,1 6,20M12,8A2,2 0 0,1 10,6A2,2 0 0,1 12,4A2,2 0 0,1 14,6A2,2 0 0,1 12,8M12,20A2,2 0 0,1 10,18A2,2 0 0,1 12,16A2,2 0 0,1 14,18A2,2 0 0,1 12,20M18,8A2,2 0 0,1 16,6A2,2 0 0,1 18,4A2,2 0 0,1 20,6A2,2 0 0,1 18,8M18,20A2,2 0 0,1 16,18A2,2 0 0,1 18,16A2,2 0 0,1 20,18A2,2 0 0,1 18,20M12,14A2,2 0 0,1 10,12A2,2 0 0,1 12,10A2,2 0 0,1 14,12A2,2 0 0,1 12,14Z"/>
          </svg>
          <span class="text-xs font-medium">Apps</span>
        </button>

        <!-- Arcade Tab -->
        <button 
          class="flex flex-col items-center py-2 px-4"
          :class="activeTab === 'arcade' ? 'text-blue-400' : 'text-gray-400'"
          @click="activeTab = 'arcade'"
        >
          <svg class="w-6 h-6 mb-1" fill="currentColor" viewBox="0 0 24 24">
            <path d="M17.5,12A1.5,1.5 0 0,1 16,10.5A1.5,1.5 0 0,1 17.5,9A1.5,1.5 0 0,1 19,10.5A1.5,1.5 0 0,1 17.5,12M14.5,15A1.5,1.5 0 0,1 13,13.5A1.5,1.5 0 0,1 14.5,12A1.5,1.5 0 0,1 16,13.5A1.5,1.5 0 0,1 14.5,15M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M12,20C7.59,20 4,16.41 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,16.41 16.41,20 12,20M6.5,10L8,8.5L9.5,10L8,11.5L6.5,10Z"/>
          </svg>
          <span class="text-xs font-medium">Arcade</span>
        </button>

        <!-- Search Tab -->
        <button 
          class="flex flex-col items-center py-2 px-4"
          :class="activeTab === 'search' ? 'text-blue-400' : 'text-gray-400'"
          @click="activeTab = 'search'"
        >
          <svg class="w-6 h-6 mb-1" fill="currentColor" viewBox="0 0 24 24">
            <path d="M9.5,3A6.5,6.5 0 0,1 16,9.5C16,11.11 15.41,12.59 14.44,13.73L14.71,14H15.5L20.5,19L19,20.5L14,15.5V14.71L13.73,14.44C12.59,15.41 11.11,16 9.5,16A6.5,6.5 0 0,1 3,9.5A6.5,6.5 0 0,1 9.5,3M9.5,5C7,5 5,7 5,9.5C5,12 7,14 9.5,14C12,14 14,12 14,9.5C14,7 12,5 9.5,5Z"/>
          </svg>
          <span class="text-xs font-medium">Search</span>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.font-sans {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'SF Pro Display', sans-serif;
}
</style>
