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
        <!-- Sekcja Zalety Chart.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Chart.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Prostota użycia:</strong>
                        Chart.js jest łatwy w użyciu, umożliwiając szybkie tworzenie interaktywnych wykresów.
                    </li>
                    <li>
                        <strong class="text-green-400">Duża ilość typów wykresów:</strong>
                        Biblioteka obsługuje różne typy wykresów, takie jak liniowe, słupkowe, kołowe i inne.
                    </li>
                    <li>
                        <strong class="text-green-400">Dostosowywalność:</strong>
                        Chart.js oferuje szerokie możliwości dostosowania wykresów do własnych potrzeb.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Chart.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Chart.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Ograniczone możliwości 3D:</strong>
                        Chart.js nie obsługuje wykresów 3D.
                    </li>
                    <li>
                        <strong class="text-red-400">Niektóre problemy z wydajnością:</strong>
                        Może wystąpić spadek wydajności przy renderowaniu dużej ilości danych.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Chart.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 border-teal-400 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Chart.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Tworzenie wykresu liniowego</h3>
                <p class="text-red-400">Przykład tworzenia wykresu liniowego przy użyciu Chart.js.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Chart.js dla wykresu liniowego */}</span>
      <span class="text-blue-400">&lt;script src="https://cdn.jsdelivr.net/npm/chart.js"&gt;&lt;/script&gt;</span>
      <span class="text-blue-400">&lt;canvas id="myChart" width="400" height="200"&gt;&lt;/canvas&gt;</span>
      <span class="text-blue-400">&lt;script&gt;</span>
        <span class="text-lightblue-300">const ctx = document.getElementById('myChart').getContext('2d');</span>
        <span class="text-lightblue-300">const myChart = new Chart(ctx, {</span>
          <span class="text-lightblue-300">type: 'line',</span>
          <span class="text-lightblue-300">data: {</span>
            <span class="text-lightblue-300">labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],</span>
            <span class="text-lightblue-300">datasets: [{</span>
              <span class="text-lightblue-300">label: '# of Votes',</span>
              <span class="text-lightblue-300">data: [12, 19, 3, 5, 2, 3]</span>
            <span class="text-lightblue-300">}]</span>
          <span class="text-lightblue-300">}</span>
        <span class="text-lightblue-300">});</span>
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