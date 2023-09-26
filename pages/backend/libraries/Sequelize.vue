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
        <!-- Sekcja Zalety Sequelize -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Sequelize</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Wsparcie dla wielu dialektów:</strong>
                        Sequelize obsługuje wiele dialektów SQL, takich jak PostgreSQL, MySQL, SQLite i MSSQL.
                    </li>
                    <li>
                        <strong class="text-green-400">Asynchroniczność:</strong>
                        Sequelize jest biblioteką asynchroniczną, co pozwala na łatwą integrację z innymi bibliotekami asynchronicznymi.
                    </li>
                    <li>
                        <strong class="text-green-400">Modelowanie obiektów:</strong>
                        Sequelize oferuje potężne funkcje modelowania obiektów i walidację danych.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Sequelize -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Sequelize</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Kompleksowość:</strong>
                        Sequelize może być skomplikowany dla nowych użytkowników z powodu swojej rozbudowanej funkcjonalności.
                    </li>
                    <li>
                        <strong class="text-red-400">Wyższe zużycie zasobów:</strong>
                        Może zużywać więcej zasobów w porównaniu z lżejszymi bibliotekami ORM.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Sequelize -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Sequelize</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Definiowanie Modelu</h3>
                <p class="text-red-400">Definiowanie modelu dla użytkownika w Sequelize.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
      <code class="user-select py-4">
        <span class="text-green-500">{/* Przykład kodu Sequelize dla modelu */}</span>

        <span class="text-blue-400">const</span> { Sequelize } <span class="text-blue-400">= require('sequelize');</span>
        <span class="text-blue-400">const sequelize = new Sequelize('database', 'username', 'password');</span>

        <span class="text-blue-400">const User = sequelize.define('user', {</span>
          <span class="text-blue-400">username: Sequelize.STRING,</span>
          <span class="text-blue-400">email: Sequelize.STRING</span>
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
    box-shadow: rgb(54, 54, 255) 0 0 25px;
}
</style>
