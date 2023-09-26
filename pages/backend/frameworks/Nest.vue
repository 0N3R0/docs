<script setup>
import { useRoute } from 'vue-router';
const route = useRoute();

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

<template>
    <div class="u-select w-full">
        <!-- Sekcja Zalety Nest.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Nest.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Architektura modularna:</strong>
                        Nest.js zapewnia modularną architekturę, która ułatwia organizację kodu.
                    </li>
                    <li>
                        <strong class="text-green-400">Wsparcie dla TypeScript:</strong>
                        Nest.js jest zbudowany z myślą o TypeScript, co pozwala na korzystanie z silnych typów i nowoczesnych funkcji języka.
                    </li>
                    <li>
                        <strong class="text-green-400">Elastyczność:</strong>
                        Nest.js pozwala na używanie różnych bibliotek i narzędzi, co daje dużą elastyczność.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Nest.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Nest.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Krzywa uczenia się:</strong>
                        Nest.js ma stosunkowo stromą krzywą uczenia się z powodu swojej zaawansowanej architektury.
                    </li>
                    <li>
                        <strong class="text-red-400">Młody ekosystem:</strong>
                        Jako że jest to stosunkowo nowy framework, niektóre funkcje lub biblioteki mogą być jeszcze niedopracowane.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Nest.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Nest.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Tworzenie prostego serwera</h3>
                <p class="text-red-400">Przykład tworzenia prostego serwera HTTP przy użyciu Nest.js.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Nest.js dla prostego serwera */}</span>
      <span class="text-blue-400">import</span> { NestFactory } <span class="text-blue-400">from</span> <span class="text-purple-400">'@nestjs/core';</span>
      <span class="text-blue-400">import</span> { AppModule } <span class="text-blue-400">from</span> <span class="text-purple-400">'./app.module';</span>

      <span class="text-blue-400">async function</span> <span class="text-blue-400">bootstrap() {</span>
        <span class="text-blue-400">const app = await NestFactory.create(AppModule);</span>
        <span class="text-blue-400">await app.listen(3000);</span>
        <span class="text-blue-400">console.log('Server started on port 3000');</span>
      <span class="text-blue-400">}</span>
      <span class="text-blue-400">bootstrap();</span>
    </code>
  </pre>
            </div>
        </section>
    </div>
</template>
<style scoped>
* {
    user-select: none;
}

.user-select {
    user-select: all !important;
}

code>span,
code>span>span {
    user-select: all;
}

.code-shadow {
    box-shadow: #f87171 0 0 3px;
}

.text-green-500 {
    color: #2ecc71;
}

.text-blue-400 {
    color: #3498db;
}

.text-purple-400,
.text-purple-300 {
    color: #9b59b6;
}

.text-lightblue-300 {
    color: #1abc9c;
}

.border-red-400 {
    border-color: #e74c3c;
}

pre {
    background-color: #0d1117e7;
    backdrop-filter: blur(5px);
    box-shadow: black 0 0 15px;
    border-radius: 6px;
    padding: 16px;
    padding-top: 32px;
    padding-bottom: 16px;
}

code {
    color: #c9d1d9;
    font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, monospace;
    font-size: 12px;
}

.code-section {
    background-image: url('~/assets/media/sails-hero-code.jpg');
    box-shadow: red 0 0 25px;
}
</style>