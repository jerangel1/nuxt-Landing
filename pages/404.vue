<template>
    <NuxtLayout>
        <div class="min-h-[calc(100vh-80px)] flex items-center justify-center bg-white dark:bg-gray-900">
            <div class="max-w-2xl mx-auto px-4 py-16 text-center">
                <div class="relative w-full max-w-lg mx-auto mb-12">
                    <div class="absolute inset-0 bg-gradient-to-r from-primary/20 to-[#8cd66a]/20 blur-3xl rounded-full"></div>
                    <img 
                        src="https://betsol-web.s3.us-east-2.amazonaws.com/couldron-404.avif" 
                        alt="Caldero vacío" 
                        class="relative z-10 w-full h-auto animate-float mx-auto"
                    />
                </div>
                
                <h1 class="text-7xl font-bold text-gray-900 dark:text-white mb-6">
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-[#8cd66a]">
                        404
                    </span>
                </h1>
                
                <p class="text-2xl text-gray-600 dark:text-gray-300 mb-12">
                    ¡Vaya! Parece que este caldero está vacío. <br>
                    ¿Seguro que no buscabas la olla de oro en otro lado? 🍀
                </p>
                
                <div class="flex flex-col sm:flex-row justify-center gap-4">
                    <NuxtLink 
                        to="/" 
                        class="px-8 py-4 bg-primary text-white rounded-xl text-lg font-medium hover:bg-primary/90 transition-colors duration-300 shadow-lg hover:shadow-xl"
                    >
                        Volver al Inicio
                    </NuxtLink>
                    <NuxtLink 
                        to="/resultados" 
                        class="px-8 py-4 bg-primary/10 text-primary rounded-xl text-lg font-medium hover:bg-primary/20 transition-colors duration-300"
                    >
                        Ver Resultados
                    </NuxtLink>
                </div>
            </div>
        </div>
    </NuxtLayout>
</template>

<script setup>
definePageMeta({
    layout: 'default'
})
</script>

<style scoped>
@keyframes float {
    0%, 100% {
        transform: translateY(0) rotate(0deg);
    }
    25% {
        transform: translateY(-15px) rotate(-2deg);
    }
    75% {
        transform: translateY(-5px) rotate(2deg);
    }
}

.animate-float {
    animation: float 6s ease-in-out infinite;
}
</style>
