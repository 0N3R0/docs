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
        <!-- Sekcja Zalety Angulara -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Angulara</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Jednolitość:</strong>
                        Angular zapewnia jednolite rozwiązania i techniki programistyczne.
                    </li>
                    <li>
                        <strong class="text-green-400">Szerokie wsparcie społeczności:</strong>
                        Angular jest utrzymywany przez Google, co gwarantuje stałe wsparcie.
                    </li>
                    <li>
                        <strong class="text-green-400">RxJS:</strong>
                        Angular korzysta z biblioteki RxJS, która ułatwia zarządzanie stanem aplikacji.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Angulara -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Angulara</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Krzywa uczenia się:</strong>
                        Angular ma stosunkowo stromą krzywą uczenia się, zwłaszcza dla początkujących programistów.
                    </li>
                    <li>
                        <strong class="text-red-400">Złożoność:</strong>
                        Czasami Angular może być postrzegany jako zbyt skomplikowany dla prostych projektów.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Angulara -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Angulara</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Aplikacja E-commerce</h3>
                <p class="text-red-400">Budowanie skomplikowanej aplikacji e-commerce z zarządzaniem stanem i routingiem.
                </p>
                <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu Angular dla aplikacji e-commerce */}</span>
      <span class="text-blue-400">import</span> { Component } <span class="text-blue-400">from</span> <span class="text-purple-400">'@angular/core'</span>;
      <span class="text-blue-400">@Component({</span>
        <span class="text-blue-400">selector:</span> <span class="text-purple-400">'app-root',</span>
        <span class="text-blue-400">templateUrl:</span> <span class="text-purple-400">'./app.component.html',</span>
        <span class="text-blue-400">styleUrls:</span> [<span class="text-purple-400">'./app.component.css'</span>]
      <span class="text-blue-400">})</span>
      <span class="text-blue-400">export class</span> AppComponent {
        <span class="text-blue-400">title</span> <span class="text-blue-400">=</span> <span class="text-purple-400">'my-e-commerce-app'</span>;
      }</code>
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
