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
        <!-- Sekcja Zalety Mongoose -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Mongoose</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Schematy:</strong>
                        Mongoose umożliwia definiowanie struktury dokumentów za pomocą schematów.
                    </li>
                    <li>
                        <strong class="text-green-400">Walidacja danych:</strong>
                        Zapewnia walidację danych i asercje typów przed zapisaniem dokumentu w bazie danych.
                    </li>
                    <li>
                        <strong class="text-green-400">Zapytania:</strong>
                        Ułatwia tworzenie złożonych zapytań do MongoDB.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Mongoose -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Mongoose</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Wyższe zużycie zasobów:</strong>
                        Mongoose może zużywać więcej zasobów niż natywne sterowniki MongoDB.
                    </li>
                    <li>
                        <strong class="text-red-400">Dodatkowa warstwa abstrakcji:</strong>
                        Dodaje dodatkową warstwę abstrakcji, co może komplikować niektóre operacje.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Mongoose -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Mongoose</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Definiowanie Schematu i Modelu</h3>
                <p class="text-red-400">Tworzenie schematu i modelu dla dokumentu użytkownika w Mongoose.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
      <code class="user-select py-4">
        <span class="text-green-500">{/* Przykład kodu Mongoose dla schematu i modelu */}</span>

        <span class="text-blue-400">const</span> mongoose <span class="text-blue-400">= require('mongoose');</span>
        <span class="text-blue-400">const</span> Schema <span class="text-blue-400">= mongoose.Schema;</span>

        <span class="text-blue-400">const userSchema = new Schema({</span>
          <span class="text-blue-400">username: String,</span>
          <span class="text-blue-400">email: String,</span>
          <span class="text-blue-400">password: String</span>
        <span class="text-blue-400">});</span>

        <span class="text-blue-400">const User = mongoose.model('User', userSchema);</span>
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
