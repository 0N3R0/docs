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
    <!-- Sekcja Zalety Reacta -->
    <div class="flex">
      <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
        <h2 class="text-2xl mb-4 text-green-400">Zalety Reacta</h2>
        <ul class="list-disc pl-5">
          <li>
            <strong class="text-green-400">Łatwość nauki:</strong>
            Jako framework do tworzenia interfejsów użytkownika, React jest prosty do nauczenia się dla osób już
            zaznajomionych z JavaScriptem.
          </li>
          <li>
            <strong class="text-green-400">Szybkość i wydajność:</strong>
            Dzięki wirtualnemu DOM, React zapewnia optymalną wydajność poprzez minimalizację operacji na rzeczywistym DOM.
          </li>
          <li>
            <strong class="text-green-400">Bogaty ekosystem:</strong>
            Z mnogością dostępnych bibliotek i narzędzi, React oferuje potężne możliwości rozbudowy i personalizacji.
          </li>
        </ul>
      </section>

      <!-- Sekcja Wady Reacta -->
      <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
        <h2 class="text-2xl mb-4 text-red-400">Wady Reacta</h2>
        <ul class="list-disc pl-5">
          <li>
            <strong class="text-red-400">Złożoność konfiguracji:</strong>
            Skonfigurowanie środowiska pod Reacta może być dla niektórych użytkowników wyzwaniem, zwłaszcza na początku.
          </li>
          <li>
            <strong class="text-red-400">Duże zapotrzebowanie na zasoby:</strong>
            React i związane z nim biblioteki często wymagają dużej ilości zasobów i pamięci.
          </li>
        </ul>
      </section>
    </div>
    <!-- Sekcja Przykłady Zastosowania Reacta -->
    <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
      class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
      <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Reacta</h2>
      <div>
        <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Aplikacja ToDo</h3>
        <p class="text-red-400">Prosta aplikacja do zarządzania listą zadań.</p>
        <pre class="rounded mt-8 text-white px-4 py-4">
    <code class="user-select py-4"><span class="text-green-500">{/* Przykład kodu React dla aplikacji ToDo */}</span>
      <span class="text-blue-400">import</span> React, { useState } <span class="text-blue-400">from</span> <span class="text-purple-400">'react'</span>;
      <span class="text-blue-400">function</span> App() {
        <span class="text-lightblue-300">const</span> [todos, setTodos] <span class="text-blue-400">=</span> useState([]);
        <span class="text-lightblue-300">const</span> handleAddTodo <span class="text-blue-400">=</span> todo <span class="text-blue-400">=&gt;</span> setTodos(prevTodos <span class="text-blue-400">=&gt;</span> [...prevTodos, todo]);
        <span class="text-lightblue-300">const</span> handleAdd = <span class="text-blue-400">() =&gt;</span> handleAddTodo(prompt('Enter a todo'));
        <span class="text-blue-400">return</span> (
          <span class="text-purple-300">&lt;div&gt;</span>
            <span class="text-purple-300">&lt;ul&gt;</span>
              {todos.map((todo, index) <span class="text-blue-400">=&gt;</span> (
                <span class="text-purple-300">&lt;li key={todo + index}&gt;</span>{todo}<span class="text-purple-300">&lt;/li&gt;</span>
              ))}
            <span class="text-purple-300">&lt;/ul&gt;</span>
            <span class="text-purple-300">&lt;button onClick={handleAdd} class="my-button"&gt;</span>Add Todo<span class="text-purple-300">&lt;/button&gt;</span>
          <span class="text-purple-300">&lt;/div&gt;</span>
        );
      }
      <span class="text-blue-400">export default</span> App;</code>
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
