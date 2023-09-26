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
        <!-- Sekcja Zalety jQuery -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety jQuery</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Łatwość użycia:</strong>
                        jQuery oferuje prosty i łatwy do zrozumienia składnię, co ułatwia szybkie pisanie skryptów.
                    </li>
                    <li>
                        <strong class="text-green-400">Wsparcie społeczności:</strong>
                        Dzięki dużemu i aktywnemu społeczeństwu, użytkownicy mogą korzystać z szerokiej gamy pluginów i
                        bibliotek.
                    </li>
                    <li>
                        <strong class="text-green-400">Kompatybilność z przeglądarkami:</strong>
                        jQuery jest kompatybilne z większością współczesnych przeglądarek internetowych.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady jQuery -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady jQuery</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Wydajność:</strong>
                        jQuery może być wolniejsze w porównaniu z czystym JavaScript, zwłaszcza w przypadku dużych
                        projektów.
                    </li>
                    <li>
                        <strong class="text-red-400">Rozmiar biblioteki:</strong>
                        Dodatkowy ciężar biblioteki jQuery może wpływać na czas ładowania strony.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania jQuery -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 border-teal-400 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania jQuery</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Animacja elementów</h3>
                <p class="text-red-400">Prosty przykład animacji elementów przy użyciu jQuery.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu jQuery dla animacji elementów */}</span>
      <span class="text-blue-400">&lt;script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"&gt;&lt;/script&gt;</span>
      <span class="text-blue-400">&lt;script&gt;</span>
        <span class="text-lightblue-300">$(document).ready(function(){</span>
          <span class="text-lightblue-300">$(".my-button").click(function(){</span>
            <span class="text-lightblue-300">$("p").slideToggle();</span>
          <span class="text-lightblue-300">});</span>
        <span class="text-lightblue-300">});</span>
      <span class="text-blue-400">&lt;/script&gt;</span></code>
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
