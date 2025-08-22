<script setup lang="ts">
import { ref } from 'vue'

const activeTab = ref('today')
const activeView = ref('today') // 'today', 'search', 'appDetail'
const searchQuery = ref('figma')
const selectedApp = ref({
  name: 'Figma',
  developer: 'Figma Inc.',
  category: 'Utilities',
  icon: 'https://api.builder.io/api/v1/image/assets/TEMP/13552704def85846e213c39a12291cc8d162177b?width=228',
  rating: 4,
  ratingCount: '4,3K',
  age: '4+',
  screenshots: [
    'https://api.builder.io/api/v1/image/assets/TEMP/da1b1cd6ed043ac2803c846ab9ef87acf383c778?width=442',
    'https://api.builder.io/api/v1/image/assets/TEMP/bd7bf5590c30903d2058d5667a6c57fbc924a038?width=442'
  ],
  features: [
    'See Figma designs and updates in real-time on any device',
    'Works over any internet connection on any number of devices'
  ]
})

const openAppDetail = (app: any) => {
  selectedApp.value = app
  activeView.value = 'appDetail'
}

const goBackToSearch = () => {
  activeView.value = 'search'
}

const goToSearch = () => {
  activeTab.value = 'search'
  activeView.value = 'search'
}

const goToToday = () => {
  activeTab.value = 'today'
  activeView.value = 'today'
}
</script>

<template>
  <div class="min-h-screen bg-black text-white font-sans overflow-hidden">
    <!-- Top Bar - Today -->
    <div v-if="activeView === 'today'" class="pt-16 pb-6 px-4">
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

    <!-- Top Bar - Search -->
    <div v-if="activeView === 'search'" class="bg-gray-900 border-b border-gray-800">
      <div class="pt-12 pb-4 px-4">
        <div class="flex items-center gap-3">
          <!-- Search Input -->
          <div class="flex-1 relative">
            <div class="bg-gray-700 rounded-lg px-4 py-2 flex items-center">
              <svg class="w-4 h-4 text-gray-400 mr-3" fill="currentColor" viewBox="0 0 16 16">
                <path d="M6.3833 12.8767C7.76953 12.8767 9.04785 12.4285 10.0938 11.6814L14.0283 15.616C14.2109 15.7986 14.4517 15.8899 14.709 15.8899C15.2485 15.8899 15.6304 15.4749 15.6304 14.9436C15.6304 14.6946 15.5474 14.4539 15.3647 14.2795L11.4551 10.3616C12.2769 9.28247 12.7666 7.94604 12.7666 6.49341C12.7666 2.98218 9.89453 0.110107 6.3833 0.110107C2.88037 0.110107 0 2.97388 0 6.49341C0 10.0046 2.87207 12.8767 6.3833 12.8767ZM6.3833 11.4988C3.64404 11.4988 1.37793 9.23267 1.37793 6.49341C1.37793 3.75415 3.64404 1.48804 6.3833 1.48804C9.12256 1.48804 11.3887 3.75415 11.3887 6.49341C11.3887 9.23267 9.12256 11.4988 6.3833 11.4988Z"/>
              </svg>
              <input
                v-model="searchQuery"
                type="text"
                class="bg-transparent text-gray-100 flex-1 outline-none text-base"
                placeholder="Search"
              />
              <button v-if="searchQuery" @click="searchQuery = ''" class="ml-2 text-gray-400">
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/>
                </svg>
              </button>
            </div>
          </div>
          <!-- Cancel Button -->
          <button
            @click="goToToday()"
            class="text-blue-400 font-medium text-base px-2"
          >
            Cancel
          </button>
        </div>
      </div>
    </div>

    <!-- Top Bar - App Detail -->
    <div v-if="activeView === 'appDetail'" class="pt-12 pb-4 px-4">
      <button @click="goBackToSearch()" class="flex items-center text-blue-400">
        <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
          <path d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.42-1.41L7.83 13H20v-2z"/>
        </svg>
        <span class="text-base font-medium">Search</span>
      </button>
    </div>

    <!-- Main Content - Today -->
    <div v-if="activeView === 'today'" class="px-4 pb-24">
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

    <!-- Main Content - Search -->
    <div v-if="activeView === 'search'" class="px-4 pb-24 bg-black">
      <!-- Figma App Result -->
      <div class="mb-8">
        <!-- App Info -->
        <div class="flex items-center justify-between mb-4">
          <div class="flex items-center space-x-4">
            <!-- App Icon -->
            <div class="w-15 h-15 rounded-xl border border-gray-600 overflow-hidden flex-shrink-0">
              <img
                src="https://api.builder.io/api/v1/image/assets/TEMP/39ae04fdd27899cbbaf3181816d897ad3301e9fe?width=120"
                alt="Figma Icon"
                class="w-full h-full object-cover"
              />
            </div>

            <!-- App Details -->
            <div class="flex-1 min-w-0">
              <h3 class="text-white text-base font-medium mb-1">Figma</h3>
              <p class="text-gray-400 text-sm mb-1">Utilities</p>
              <div class="flex items-center space-x-2">
                <!-- Star Rating -->
                <div class="flex items-center">
                  <span class="text-gray-400 text-xs">★★★★☆</span>
                </div>
                <span class="text-gray-400 text-xs">4,3K</span>
              </div>
            </div>
          </div>

          <!-- Get Button -->
          <button
            @click="openAppDetail({
              name: 'Figma',
              developer: 'Figma Inc.',
              category: 'Utilities',
              icon: 'https://api.builder.io/api/v1/image/assets/TEMP/13552704def85846e213c39a12291cc8d162177b?width=228',
              rating: 4,
              ratingCount: '4,3K',
              age: '4+',
              screenshots: [
                'https://api.builder.io/api/v1/image/assets/TEMP/da1b1cd6ed043ac2803c846ab9ef87acf383c778?width=442',
                'https://api.builder.io/api/v1/image/assets/TEMP/bd7bf5590c30903d2058d5667a6c57fbc924a038?width=442'
              ],
              features: [
                'See Figma designs and updates in real-time on any device',
                'Works over any internet connection on any number of devices'
              ]
            })"
            class="bg-gray-700 hover:bg-gray-600 transition-colors px-6 py-2 rounded-full"
          >
            <span class="text-blue-400 font-bold text-sm tracking-wider">
              GET
            </span>
          </button>
        </div>

        <!-- App Screenshots -->
        <div class="flex space-x-2 overflow-x-auto pb-2">
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/a333930f8c915decb6e0247189fc34b3e1b3d7c4?width=214"
            alt="Figma Screenshot 1"
            class="w-24 h-52 rounded-xl border border-gray-700 flex-shrink-0 object-cover"
          />
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/c008fc28d45250bf1a481fd96142843589705843?width=214"
            alt="Figma Screenshot 2"
            class="w-24 h-52 rounded-xl border border-gray-700 flex-shrink-0 object-cover"
          />
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/9650934148122d0b92406b7162e88f0106e7a84e?width=214"
            alt="Figma Screenshot 3"
            class="w-24 h-52 rounded-xl border border-gray-700 flex-shrink-0 object-cover"
          />
        </div>
      </div>

      <!-- Apple Developer App Result -->
      <div class="bg-white rounded-xl p-4 mb-4">
        <!-- App Info -->
        <div class="flex items-center justify-between mb-4">
          <div class="flex items-center space-x-4">
            <!-- App Icon -->
            <div class="w-15 h-15 rounded-xl border border-gray-300 overflow-hidden flex-shrink-0">
              <img
                src="https://api.builder.io/api/v1/image/assets/TEMP/32c7382cc95622e8029350ed18962c21280a4455?width=120"
                alt="Apple Developer Icon"
                class="w-full h-full object-cover"
              />
            </div>

            <!-- App Details -->
            <div class="flex-1 min-w-0">
              <h3 class="text-black text-base font-medium mb-1">Apple Developer</h3>
              <p class="text-gray-600 text-sm mb-1">Developer Tools</p>
              <div class="flex items-center space-x-2">
                <!-- Star Rating -->
                <div class="flex items-center">
                  <span class="text-gray-400 text-xs">★★★★☆</span>
                </div>
                <span class="text-gray-400 text-xs">4,3K</span>
              </div>
            </div>
          </div>

          <!-- Cloud Download Icon -->
          <button class="text-blue-500 text-2xl">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
              <path d="M19.35 10.04A7.49 7.49 0 0 0 12 4C9.11 4 6.6 5.64 5.35 8.04A5.994 5.994 0 0 0 0 14c0 3.31 2.69 6 6 6h13c2.76 0 5-2.24 5-5 0-2.64-2.05-4.78-4.65-4.96zM14 13v4h-4v-4H7l5-5 5 5h-3z"/>
            </svg>
          </button>
        </div>

        <!-- App Screenshots -->
        <div class="flex space-x-2 overflow-x-auto pb-2">
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/56f2b797d1e0f4f8bb6afb3f31c6d38026290c01?width=214"
            alt="Apple Developer Screenshot 1"
            class="w-24 h-52 rounded-xl border border-gray-300 flex-shrink-0 object-cover"
          />
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/a5aa3230c8ae0d0e86f3890bed2ea6be2fdb9be4?width=214"
            alt="Apple Developer Screenshot 2"
            class="w-24 h-52 rounded-xl border border-gray-300 flex-shrink-0 object-cover"
          />
          <img
            src="https://api.builder.io/api/v1/image/assets/TEMP/2f4f728b284baa9d7a6f5920495a55e2e0d9dccd?width=214"
            alt="Apple Developer Screenshot 3"
            class="w-24 h-52 rounded-xl border border-gray-300 flex-shrink-0 object-cover"
          />
        </div>
      </div>
    </div>

    <!-- Main Content - App Detail -->
    <div v-if="activeView === 'appDetail'" class="px-4 pb-24 bg-black">
      <!-- App Header -->
      <div class="flex items-start space-x-4 mb-6">
        <!-- Large App Icon -->
        <div class="w-28 h-28 rounded-3xl border border-gray-600 overflow-hidden flex-shrink-0">
          <img
            :src="selectedApp.icon"
            :alt="selectedApp.name + ' Icon'"
            class="w-full h-full object-cover"
          />
        </div>

        <!-- App Info -->
        <div class="flex-1 pt-2">
          <h1 class="text-white text-xl font-semibold mb-1">{{ selectedApp.name }}</h1>
          <p class="text-gray-400 text-base mb-4">{{ selectedApp.developer }}</p>

          <!-- Action Buttons -->
          <div class="flex items-center space-x-3">
            <button class="bg-blue-500 hover:bg-blue-600 transition-colors px-6 py-2 rounded-2xl">
              <span class="text-white font-semibold text-base">
                GET
              </span>
            </button>
            <button class="text-blue-400 text-xl">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M18 16.08c-.76 0-1.44.3-1.96.77L8.91 12.7c.05-.23.09-.46.09-.7s-.04-.47-.09-.7l7.05-4.11c.54.5 1.25.81 2.04.81 1.66 0 3-1.34 3-3s-1.34-3-3-3-3 1.34-3 3c0 .24.04.47.09.7L8.04 9.81C7.5 9.31 6.79 9 6 9c-1.66 0-3 1.34-3 3s1.34 3 3 3c.79 0 1.5-.31 2.04-.81l7.12 4.16c-.05.21-.08.43-.08.65 0 1.61 1.31 2.92 2.92 2.92 1.61 0 2.92-1.31 2.92-2.92s-1.31-2.92-2.92-2.92z"/>
              </svg>
            </button>
          </div>
        </div>
      </div>

      <!-- App Stats -->
      <div class="border-t border-gray-700 pt-4 mb-6">
        <div class="flex justify-around">
          <!-- Ratings -->
          <div class="text-center">
            <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">{{ selectedApp.ratingCount }} RATINGS</p>
            <div class="text-gray-400 text-xl font-semibold mb-1">{{ selectedApp.rating }}</div>
            <div class="flex items-center justify-center">
              <span class="text-gray-400 text-sm">★★★★☆</span>
            </div>
          </div>

          <!-- Separator -->
          <div class="w-px bg-gray-600 h-12 self-center"></div>

          <!-- Age -->
          <div class="text-center">
            <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">AGE</p>
            <div class="text-gray-400 text-xl font-semibold mb-1">{{ selectedApp.age }}</div>
            <p class="text-gray-500 text-sm">Years Old</p>
          </div>

          <!-- Separator -->
          <div class="w-px bg-gray-600 h-12 self-center"></div>

          <!-- Category -->
          <div class="text-center">
            <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">CATEGORY</p>
            <div class="text-gray-400 text-xl mb-1">
              <svg class="w-6 h-6 mx-auto" fill="currentColor" viewBox="0 0 24 24">
                <path d="M22.7 19l-9.1-9.1c.9-2.3.4-5-1.5-6.9-2-2-5-2.4-7.4-1.3L9 6 6 9 1.6 4.7C.4 7.1.9 10.1 2.9 12.1c1.9 1.9 4.6 2.4 6.9 1.5l9.1 9.1c.4.4 1 .4 1.4 0l2.3-2.3c.5-.4.5-1.1.1-1.4z"/>
              </svg>
            </div>
            <p class="text-gray-500 text-sm">{{ selectedApp.category }}</p>
          </div>

          <!-- Separator -->
          <div class="w-px bg-gray-600 h-12 self-center"></div>

          <!-- Developer -->
          <div class="text-center">
            <p class="text-gray-400 text-xs font-semibold uppercase tracking-wider mb-1">DEVELOPER</p>
            <div class="text-gray-400 text-xl mb-1">
              <svg class="w-6 h-6 mx-auto" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
              </svg>
            </div>
            <p class="text-gray-500 text-sm">{{ selectedApp.developer }}</p>
          </div>
        </div>
      </div>

      <!-- Feature Descriptions -->
      <div class="mb-6">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
          <div v-for="(feature, index) in selectedApp.features" :key="index">
            <p class="text-gray-300 text-sm leading-relaxed">{{ feature }}</p>
          </div>
        </div>
      </div>

      <!-- Screenshots Gallery -->
      <div class="flex space-x-2 overflow-x-auto pb-4">
        <img
          v-for="(screenshot, index) in selectedApp.screenshots"
          :key="index"
          :src="screenshot"
          :alt="selectedApp.name + ' Screenshot ' + (index + 1)"
          class="w-56 h-96 rounded-3xl flex-shrink-0 object-cover"
        />
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
