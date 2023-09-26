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
        <!-- Sekcja Zalety Passport.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Passport.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Łatwość integracji:</strong>
                        Passport.js jest łatwy do zintegrowania z różnymi frameworkami opartymi na Express.js.
                    </li>
                    <li>
                        <strong class="text-green-400">Elastyczność:</strong>
                        Umożliwia korzystanie z wielu strategii uwierzytelniania.
                    </li>
                    <li>
                        <strong class="text-green-400">Rozszerzalność:</strong>
                        Posiada wiele dostępnych strategii uwierzytelniania.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Passport.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Passport.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Dokumentacja:</strong>
                        Niektóre strategie mogą mieć ograniczoną dokumentację.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Passport.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Passport.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Uwierzytelnianie lokalne</h3>
                <p class="text-red-400">Przykład uwierzytelniania lokalnego z wykorzystaniem Passport.js.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
      <code class="user-select py-4">
        <span class="text-green-500">{/* Przykład kodu Passport.js dla uwierzytelniania lokalnego */}</span>

        <span class="text-blue-400">const</span> passport <span class="text-blue-400">= require('passport');</span>
        <span class="text-blue-400">const</span> LocalStrategy <span class="text-blue-400">= require('passport-local').Strategy;</span>

        <span class="text-blue-400">passport.use(new LocalStrategy({</span>
          <span class="text-blue-400">usernameField: 'email'</span>
        <span class="text-blue-400">}, (username, password, done) => {</span>
          <span class="text-blue-400">// Kod weryfikacji użytkownika</span>
        <span class="text-blue-400">}));</span>
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
