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
        <!-- Sekcja Zalety Ember.js -->
        <div class="flex">
            <section class="mb-10 mr-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-green-400">Zalety Ember.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-green-400">Konwencja nad konfiguracją:</strong>
                        Ember.js ułatwia rozwijanie aplikacji dzięki zastosowaniu konwencji, które minimalizują
                        konfigurację.
                    </li>
                    <li>
                        <strong class="text-green-400">Produktywność:</strong>
                        Zawiera zestaw narzędzi CLI do automatyzacji zadań, co zwiększa produktywność.
                    </li>
                    <li>
                        <strong class="text-green-400">Wsparcie dla Single Page Applications:</strong>
                        Zaprojektowany z myślą o budowie nowoczesnych aplikacji internetowych.
                    </li>
                </ul>
            </section>

            <!-- Sekcja Wady Ember.js -->
            <section class="mb-10 ml-8 p-8 border-2 border-yellow-200 rounded-lg shadow-md bg-neutral-800 w-2/4">
                <h2 class="text-2xl mb-4 text-red-400">Wady Ember.js</h2>
                <ul class="list-disc pl-5">
                    <li>
                        <strong class="text-red-400">Krzywa uczenia się:</strong>
                        Może być trudny do nauczenia się dla osób nieznajomych z konwencjami frameworka.
                    </li>
                    <li>
                        <strong class="text-red-400">Rozmiar:</strong>
                        Jest stosunkowo ciężki, co może wpływać na wydajność aplikacji.
                    </li>
                </ul>
            </section>
        </div>
        <!-- Sekcja Przykłady Zastosowania Ember.js -->
        <section :class="{ 'border-red-400': isFramework('frameworks'), 'border-teal-400': isLibrary('libraries') }"
            class="my-20 p-12 border-2 rounded-lg shadow-lg w-full text-sm code-section">
            <h2 class="text-3xl mb-4 text-yellow-200 neon-text">Przykłady Zastosowania Ember.js</h2>
            <div>
                <h3 class="text-2xl mb-2 text-yellow-200 neon-text">Aplikacja Bloga</h3>
                <p class="text-red-400">Budowanie zaawansowanej aplikacji bloga z autentykacją, dynamicznym routingiem, i
                    komponentami.</p>
                <pre class="rounded mt-8 text-white px-4 py-4">
      <code class="user-select py-4">
        <span class="text-green-500">{/* Przykład kodu Ember.js dla aplikacji bloga */}</span>

        <span class="text-blue-400">// app/router.js</span>
        <span class="text-blue-400">import</span> EmberRouter <span class="text-blue-400">from</span> <span class="text-purple-400">'@ember/routing/router'</span>;
        <span class="text-blue-400">export default class Router extends EmberRouter</span> {
          <span class="text-blue-400">@tracked</span> location <span class="text-blue-400">= config.locationType;</span>
        }

        <span class="text-blue-400">// app/routes/blog.js</span>
        <span class="text-blue-400">import</span> Route <span class="text-blue-400">from</span> <span class="text-purple-400">'@ember/routing/route'</span>;
        <span class="text-blue-400">export default class BlogRoute extends Route</span> {
          <span class="text-blue-400">model()</span> {
            <span class="text-blue-400">return this.store.findAll('post');</span>
          }
        }

        <span class="text-blue-400">// app/models/post.js</span>
        <span class="text-blue-400">import</span> Model, { attr } <span class="text-blue-400">from</span> <span class="text-purple-400">'@ember-data/model'</span>;
        <span class="text-blue-400">export default class PostModel extends Model</span> {
          @attr('string') title;
          @attr('string') content;
        }

        <span class="text-blue-400">// app/templates/blog.hbs</span>
        <span class="text-blue-400">&lt;ul&gt;</span>
          <span class="text-blue-400">&lt;li&gt;</span><span class="text-purple-400">each</span> <span class="text-blue-400">this.model as |post|&gt;</span>
            <span class="text-blue-400">&lt;PostComponent @post={<span class="">{ post }</span>} /&gt;</span>
          <span class="text-blue-400">&lt;/li&gt;</span>
        <span class="text-blue-400">&lt;/ul&gt;</span>

        <span class="text-blue-400">// app/components/post-component.js</span>
        <span class="text-blue-400">import</span> Component <span class="text-blue-400">from</span> <span class="text-purple-400">'@ember/component'</span>;
        <span class="text-blue-400">export default class PostComponent extends Component</span> {
        }
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