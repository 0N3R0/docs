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
        <!-- Sekcja Zalety Svelte -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Svelte</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Brak wirtualnego DOM:</strong>
                        Svelte nie używa wirtualnego DOM, co przyczynia się do zwiększenia wydajności.
                    </li>
                    <li>
                        <strong class="text-green-400">Kompilacja:</strong>
                        Svelte jest kompilowany do niewielkiego, zoptymalizowanego kodu JavaScript.
                    </li>
                    <li>
                        <strong class="text-green-400">Łatwość nauki:</strong>
                        Svelte jest prosty i łatwy do nauki, zwłaszcza dla początkujących programistów.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Svelte -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Svelte</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Mniejsza społeczność:</strong>
                        Svelte ma mniejszą społeczność w porównaniu do React czy Angular.
                    </li>
                    <li>
                        <strong class="text-red-400">Mniej bibliotek i narzędzi:</strong>
                        Ze względu na mniejszą społeczność, dostępnych jest mniej bibliotek i narzędzi.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Svelte -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Svelte</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Aplikacja pogodowa</h3>
                <p class="text-red-400">Prosta aplikacja pogodowa pokazująca aktualną pogodę w różnych lokalizacjach.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
<code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Svelte dla aplikacji pogodowej */}</span>
  <span class="text-blue-400">&lt;script&gt;</span>
    <span class="text-lightblue-300">import</span> { onMount } <span class="text-blue-400">from</span> <span class="text-purple-400">'svelte'</span>;
    <span class="text-lightblue-300">let</span> weather;
    
    onMount(<span class="text-blue-400">async</span> () <span class="text-blue-400">=&gt;</span> {
      <span class="text-lightblue-300">const</span> response <span class="text-blue-400">=</span> <span class="text-blue-400">await</span> fetch(<span class="text-purple-400">'http://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&amp;q=London'</span>);
      weather <span class="text-blue-400">=</span> <span class="text-blue-400">await</span> response.json();
    });
  <span class="text-blue-400">&lt;/script&gt;</span>

  <span class="text-purple-300">&lt;p&gt;</span>The weather in {weather?.location?.name} is {weather?.current?.condition?.text}<span class="text-purple-300">&lt;/p&gt;</span>
  <span class="text-purple-300">&lt;img src="{weather?.current?.condition?.icon}" alt="weather icon" /&gt;</span>
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