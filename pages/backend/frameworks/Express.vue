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
        <!-- Sekcja Zalety Express.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Express.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Minimalizm:</strong>
                        Express.js jest lekki i nie narzuca żadnej struktury, co pozwala na dużą elastyczność.
                    </li>
                    <li>
                        <strong class="text-green-400">Łatwość użycia:</strong>
                        Dzięki prostemu API, Express.js jest łatwy do nauczenia i użycia.
                    </li>
                    <li>
                        <strong class="text-green-400">Middleware:</strong>
                        Express.js umożliwia używanie oprogramowania pośredniczącego do obsługi żądań i odpowiedzi.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Express.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Express.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Brak niektórych funkcji:</strong>
                        Express.js nie oferuje niektórych funkcji "out-of-the-box", które są dostępne w innych frameworkach.
                    </li>
                    <li>
                        <strong class="text-red-400">Brak surowej wydajności:</strong>
                        Express.js może nie być tak szybki jak niektóre inne frameworki back-end.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Express.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Express.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Tworzenie prostego serwera</h3>
                <p class="text-red-400">Przykład tworzenia prostego serwera HTTP przy użyciu Express.js.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Express.js dla prostego serwera */}</span>
      <span class="text-blue-400">const</span> express <span class="text-blue-400">=</span> <span class="text-blue-400">require('express');</span>
      <span class="text-blue-400">const</span> app <span class="text-blue-400">=</span> <span class="text-blue-400">express();</span>

      <span class="text-blue-400">app.get('/',</span> <span class="text-blue-400">(req, res)</span> <span class="text-blue-400">=&gt; {</span>
        <span class="text-blue-400">res.send('Hello World!');</span>
      <span class="text-blue-400">});</span>

      <span class="text-blue-400">app.listen(3000,</span> <span class="text-blue-400">()</span> <span class="text-blue-400">=&gt; {</span>
        <span class="text-blue-400">console.log('Server started on port 3000');</span>
      <span class="text-blue-400">});</span>
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