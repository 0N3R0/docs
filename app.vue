<script setup>
import { useRoute } from 'vue-router';
const route = useRoute();

const isActive = (path) => route.path == path;

const isFramework = (path) => {
  const mainPath = route.path.split('/')[2];
  if (mainPath == path) {
    return true;
  }
  return false;
}

const isLibrary = (path) => {
  const mainPath = route.path.split('/')[2];
  if (mainPath == path) {
    return true;
  }
  return false;
}
</script>

<style scoped>
.nav-main {
  user-select: none;
  height: calc(100vh - 5.5rem);
  overflow: auto;
}

.nav-main::-webkit-scrollbar {
  width: 2px;
}

.nav-main::-webkit-scrollbar-track {
  background: #030613;
  border-radius: 16px;
}

.nav-main::-webkit-scrollbar-thumb {
  background-color: #fff08b;
  border-radius: 16px;
}

.framework-shadow {
  box-shadow: #dd6566 0 0 15px;
}

.library-shadow {
  box-shadow: #2cd0bb 0 0 15px;
}

.scroll-framework::-webkit-scrollbar-thumb {
  background-color: #dd6566 !important;
}

.scroll-library::-webkit-scrollbar-thumb {
  background-color: #2cd0bb !important;
}

.section-info {
  transition: 250ms ease-in-out;
}
html::-webkit-scrollbar {
  width: 6px;
}

html::-webkit-scrollbar-track {
  background: #030613;
  border-radius: 16px;
}

html::-webkit-scrollbar-thumb {
  background-color: #fff08b;
  border-radius: 16px;
}

html::-webkit-scrollbar-track {
  background: #030613;
  border-radius: 16px;
}

.sails-cover {
  background-image: url('~/assets/media/button-cover.jpg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  transition: 150ms;
}

.u-select {
  user-select: none;
}
</style>
 
<template>
  <html
    class="bg-neutral-950">
  <div class="container bg-gray-950 min-w-full min-h-screen">

    <PageheaderHeader />

    <div class="flex pt-20">
      <nav :class="{ 'scroll-framework': isFramework('frameworks'), 'scroll-library': isLibrary('libraries') }"
        class="w-40 lg:w-80 md:w-60 h-16 py-2 px-4 nav-main fixed">
        <div>
          <div class="div-top-text flex">
            <span class="span-top-text text-yellow-200 text-3xl border-b-2 border-yellow-200 w-full">
              FRONT-END
            </span>
          </div>
          <br>
          <div class="category-frames">
            <div class="category-frames-div ms-8">
              <span class="category-frame-text text-red-400 text-2xl">
                Frameworki
              </span>
            </div>
            <div class="frameworks ps-8">
              <ul class="list-none text-xl flex flex-col gap-1">
                <li>
                  <NuxtLink to="/frontend/frameworks/react">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/frameworks/react') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/react.svg" alt="Image" class="w-8"> React.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/frameworks/vue">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/frameworks/vue') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/vue.svg" alt="Image" class="w-8"> Vue.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/frameworks/ember">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/frameworks/ember') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/ember.svg" alt="Image" class="w-8"> Ember.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/frameworks/angular">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/frameworks/angular') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/angular.svg" alt="Image" class="w-8"> Angular
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/frameworks/svelte">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/frameworks/svelte') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/svelte.svg" alt="Image" class="w-8"> Svelte
                    </span>
                  </NuxtLink>
                </li>
              </ul>
            </div>
          </div>
          <br><br>
          <div class="category-libs">
            <div class="category-libs-div ms-8">
              <span class="category-libs-text text-teal-400 text-2xl">
                Biblioteki
              </span>
            </div>
            <div class="libraries ps-8">
              <ul class="list-none text-xl flex flex-col gap-1">
                <li>
                  <NuxtLink to="/frontend/libraries/jquery">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/libraries/jquery') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/jquery.png" alt="Image" class="w-8"> jQuery
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/libraries/lodash">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/libraries/lodash') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/lodash.svg" alt="Image" class="w-8"> lodash
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/libraries/axios">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/libraries/axios') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/axios.svg" alt="Image" class="w-8"> axios
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/libraries/moment">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/libraries/moment') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/moment.js.png" alt="Image" class="w-8"> moment.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/frontend/libraries/chart">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/frontend/libraries/chart') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/chart.svg" alt="Image" class="w-8"> chart.js
                    </span>
                  </NuxtLink>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <br><br>
        <div>
          <div class="div-top-text flex">
            <span class="span-top-text text-yellow-200 text-3xl border-b-2 border-yellow-200 w-full">
              BACK-END
            </span>
          </div>
          <br>
          <div class="category-frames">
            <div class="category-frames-div ms-8">
              <span class="category-frame-text text-red-400 text-2xl">
                Frameworki
              </span>
            </div>
            <div class="frameworks ps-8">
              <ul class="list-none text-xl flex flex-col gap-1">
                <li>
                  <NuxtLink to="/backend/frameworks/express">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/frameworks/express') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/express.png" alt="Image" class="w-8"> Express.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/frameworks/koa">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/frameworks/koa') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/koa.png" alt="Image" class="w-8"> Koa.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/frameworks/hapi">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/frameworks/hapi') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/hapi.svg" alt="Image" class="w-8"> Hapi.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/frameworks/sails">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/frameworks/sails') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/sails.png" alt="Image" class="w-8"> Sails.js
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/frameworks/nest">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/frameworks/nest') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-red-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-red-400 hover:border-yellow-200">
                      <img src="~/assets/media/nest.svg" alt="Image" class="w-8"> NestJS
                    </span>
                  </NuxtLink>
                </li>
              </ul>
            </div>
          </div>
          <br><br>
          <div class="category-libs">
            <div class="category-libs-div ms-8">
              <span class="category-libs-text text-teal-400 text-2xl">
                Biblioteki
              </span>
            </div>
            <div class="libraries ps-8">
              <ul class="list-none text-xl flex flex-col gap-1">
                <li>
                  <NuxtLink to="/backend/libraries/mongoose">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/libraries/mongoose') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/mongoose.png" alt="Image" class="w-8"> Mongoose
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/libraries/sequelize">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/libraries/sequelize') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/sequelize.svg" alt="Image" class="w-8"> Sequelize
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/libraries/socket">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/libraries/socket') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/socketio.svg" alt="Image" class="w-8"> Socket.io
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/libraries/nodefetch">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/libraries/nodefetch') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/nodefetch.png" alt="Image" class="w-8"> Node-fetch
                    </span>
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/backend/libraries/passport">
                    <span
                      :class="{ 'border-yellow-200 text-yellow-200 sails-cover': isActive('/backend/libraries/passport') }"
                      class="h-14 inline-block px-4 py-2 bg-gray-950 text-teal-400 hover:bg-black hover:text-yellow-200 cursor-pointer w-full rounded ease-out duration-200 flex items-center gap-2 border-[2px] border-teal-400 hover:border-yellow-200">
                      <img src="~/assets/media/passport.svg" alt="Image" class="w-8"> Passport.js
                    </span>
                  </NuxtLink>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </nav>
      <main class="u-select flex flex-col items-center w-full min-h-100 pt-[3vh] text-white pl-80" draggable="false">
        <div class="mb-32">
          <!-- Główna sekcja zawartości -->
          <div class="flex w-full justify-center px-40 xs:px-20 sm:px-28 lg:px-40">
            <!-- Sekcja frameworków -->
            <section :class="{ 'framework-shadow': isFramework('frameworks') }"
              class="section-info flex-1 mt-24 mr-8 p-8 border border-gray-300 rounded-lg shadow-md bg-neutral-800 border-2 border-red-400 w-2/4">
              <h2 class="text-2xl mb-4">Frameworki</h2>
              <p>Frameworki są zestawami narzędzi, bibliotek i najlepszych praktyk, które ułatwiają rozwój oprogramowania.
              </p>
            </section>

            <!-- Sekcja bibliotek -->
            <section :class="{ 'library-shadow': isLibrary('libraries') }"
              class="section-info flex-1 mt-24 ml-8 p-8 border border-gray-300 rounded-lg shadow-md bg-neutral-800 border-2 border-teal-400 w-2/4">
              <h2 class="text-2xl mb-4">Biblioteki</h2>
              <p>Biblioteki to zestawy narzędzi i funkcji, które można wykorzystać w różnych projektach programistycznych.
              </p>
            </section>
          </div>
        </div>

        <div class="flex flex-col w-full items-center px-40">
          <NuxtPage />
        </div>
      </main>
    </div>
  </div>

  </html>
</template>