<style scoped>
    .animate-text {
        animation: 1s animateText ease;
    }
</style>
<template>
    <header id="header" class="w-full flex justify-between tracking-widest ease-out duration-500 pl-5 md:pl-16 xl:pl-32 pt-5 pb-5 h-20 backdrop-blur-xl fixed bg-gray-950/60">
        <span class="text-2xl text-neutral-50 animate-text">
            Informacje na temat 
            
            <span id="framework" class="text-red-400">Framework</span>'ów oraz
            <span id="library" class="text-teal-400 shadow">Bibliotek</span>
            w
            <span id="javascript" class="text-yellow-200 shadow">Javascript</span>
        </span>
    </header>
</template>