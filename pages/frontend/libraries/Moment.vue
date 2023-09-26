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
    <div class="u-select">
        <!-- Sekcja Zalety Moment.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Moment.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Prostota użycia:</strong>
                        Moment.js jest łatwy do nauczenia i użycia nawet dla początkujących programistów.
                    </li>
                    <li>
                        <strong class="text-green-400">Wsparcie dla różnych formatów dat:</strong>
                        Moment.js obsługuje wiele formatów dat i czasu, co ułatwia manipulację i formatowanie dat.
                    </li>
                    <li>
                        <strong class="text-green-400">Zgodność z różnymi strefami czasowymi:</strong>
                        Moment.js umożliwia pracę z różnymi strefami czasowymi, co jest przydatne w aplikacjach globalnych.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Moment.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Moment.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Rozmiar biblioteki:</strong>
                        Moment.js jest stosunkowo dużą biblioteką, co może wpływać na czas ładowania strony.
                    </li>
                    <li>
                        <strong class="text-red-400">Brak niezależności:</strong>
                        Moment.js nie jest niezależną biblioteką i zależy od innych bibliotek.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Moment.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 border-teal-400 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Moment.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Formatowanie daty</h3>
                <p class="text-red-400">Przykład formatowania daty przy użyciu Moment.js.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Moment.js dla formatowania daty */}</span>
      <span class="text-blue-400">&lt;script src="https://cdn.jsdelivr.net/npm/moment"&gt;&lt;/script&gt;</span>
      <span class="text-blue-400">&lt;script&gt;</span>
        <span class="text-lightblue-300">const date = moment().format('MMMM Do YYYY, h:mm:ss a');</span>
        <span class="text-lightblue-300">console.log(date);</span>
      <span class="text-blue-400">&lt;/script&gt;</span>
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
    box-shadow: rgb(54, 54, 255) 0 0 25px;
}
</style>
