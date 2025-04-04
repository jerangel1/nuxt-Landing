<template>
    <section class="relative w-full min-h-screen">
        <!-- Background gradients -->
        <div class="absolute top-0 inset-x-0 h-64 flex items-start">
            <div
                class="h-24 w-2/3 bg-gradient-to-br from-primary opacity-20 blur-2xl dark:from-[#570cac] dark:invisible dark:opacity-40">
            </div>
            <div
                class="h-20 w-3/5 bg-gradient-to-r from-[#8cd66a] opacity-40 blur-2xl dark:from-[#670ccf] dark:opacity-40">
            </div>
        </div>
        
        <!-- Floating clovers animation -->
        <div class="absolute inset-0 overflow-hidden pointer-events-none">
            <div class="clover clover-1"></div>
            <div class="clover clover-2"></div>
            <div class="clover clover-3"></div>
            <div class="clover clover-4"></div>
            <div class="clover clover-5"></div>
        </div>
        
        <AtomsContainer class-name="relative">
            <div aria-hidden="true" class="absolute inset-y-0 w-44 left-0 hidden dark:flex">
                <div
                    class="h-full md:h-1/2 lg:h-full w-full bg-gradient-to-tr opacity-40 dark:blur-2xl dark:from-[#570cac] dark:opacity-20">
                </div>
            </div>
            <div
                class="grid lg:grid-cols-2 gap-10 xl:gap-14 relative pt-24 lg:max-w-none max-w-2xl md:max-w-3xl mx-auto">
                <div class="lg:py-6">
                    <div class="text-center lg:text-left">
                        <span class="px-4 py-2 rounded-full bg-primary/10 text-primary dark:bg-primary/20 animate-pulse">¡Bienvenido a Pronosticon!</span>
                        <h1 class="text-gray-800 pt-4 dark:text-white font-bold text-4xl md:text-5xl lg:text-6xl">
                            Descubre la Suerte en Cada <span
                                class="text-transparent bg-clip-text bg-gradient-to-br from-primary to-[#8cd66a] animate-gradient-x">Número</span>
                        </h1>
                    </div>

                    <p class="text-gray-600 dark:text-gray-300 pt-8 text-center lg:text-left mx-auto max-w-xl">
                        Resultados de lotería en tiempo real, pronósticos y estadísticas para ayudarte a tomar las mejores decisiones.
                    </p>

                    <div class="flex items-center gap-3 pt-9 flex-col sm:flex-row sm:w-max sm:mx-auto lg:mx-0">
                        <AtomsLinkBtn href="/resultados" variant="primary" class="w-full sm:w-max flex justify-center hover:scale-105 transition-transform">
                            Ver Resultados
                        </AtomsLinkBtn>

                        <AtomsLinkBtn href="/pronosticos" variant="costum" costum-span-class="px-6 md:px-7 hover:bg-primary/10"
                            costum-text-color="text-primary" class="hover:scale-105 transition-transform">
                            <div class="flex items-center gap-3">
                                <span class="p-2 rounded-full border border-primary animate-spin-slow">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"
                                        fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                        <path d="M21 12a9 9 0 1 1-9-9c2.52 0 4.93 1 6.74 2.74L21 8"/>
                                        <path d="M21 3v5h-5"/>
                                    </svg>
                                </span>
                                <span>
                                    Pronósticos
                                </span>
                            </div>
                        </AtomsLinkBtn>
                    </div>
                    
                    <!-- Scroll indicator -->
                    <div class="hidden lg:flex justify-center lg:justify-start mt-10">
                        <div class="animate-bounce flex flex-col items-center">
                            <span class="text-gray-500 dark:text-gray-400 text-sm mb-1">Scroll</span>
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-primary">
                                <path d="M12 5v14"></path>
                                <path d="m19 12-7 7-7-7"></path>
                            </svg>
                        </div>
                    </div>
                </div>
                
                <!-- Hero video container -->
                <div class="lg:h-full hidden md:flex">
                    <div
                        class="flex w-full h-96 min-h-[24rem] lg:min-h-[none] lg:w-full lg:h-full items-center relative"
                    >
                        <!-- Background gradient -->
                        <div
                            class="absolute z-0 top-1/2 -translate-y-1/2 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-primary to-pink-300 dark:from-[#570cac] dark:to-primary blur-2xl"
                        ></div>
                        
                        <!-- Main video container -->
                        <div
                            class="absolute w-full h-full z-10 p-4 -translate-y-1/2 top-1/2 rounded-3xl bg-white dark:bg-body shadow-lg shadow-box-shadow border border-box-border overflow-hidden"
                        >
                            <!-- Rainbow border animation -->
                            <div class="absolute inset-0 rounded-3xl rainbow-border opacity-50"></div>
                            
                            <!-- Video with preloading and caching -->
                            <div class="w-full h-full rounded-2xl overflow-hidden relative z-10">
                                <video 
                                    ref="videoElement"
                                    class="w-full h-full object-cover"
                                    autoplay
                                    loop
                                    muted
                                    playsinline
                                    preload="auto"
                                    poster="https://betsol-web.s3.us-east-2.amazonaws.com/duendeHero.avif"
                                >
                                    <source 
                                        src="https://betsol-web.s3.us-east-2.amazonaws.com/lottery-animation.mp4" 
                                        type="video/mp4"
                                    />
                                    <!-- Fallback image if video fails to load -->
                                    <img
                                        src="https://betsol-web.s3.us-east-2.amazonaws.com/duendeHero.avif"
                                        alt="Pronosticon Hero"
                                        width="500"
                                        height="auto"
                                        class="w-full h-full rounded-2xl object-contain"
                                    />
                                </video>
                            </div>
                            
                            <!-- Floating clovers animation -->
                            <div class="absolute inset-0 z-20 overflow-hidden pointer-events-none">
                                <div class="clover clover-1"></div>
                                <div class="clover clover-2"></div>
                                <div class="clover clover-3"></div>
                            </div>
                        </div>
                        
                        <!-- Secondary lottery image -->
                        <div
                            class="absolute w-2/5 h-2/5 z-20 bottom-0 -right-5 rounded-xl bg-white dark:bg-body shadow-lg shadow-box-shadow border border-box-border overflow-hidden"
                        >
                            <img
                                src="https://betsol-web.s3.us-east-2.amazonaws.com/florida-lottery.avif"
                                alt="Lottery Results"
                                width="200"
                                height="auto"
                                loading="lazy"
                                class="w-full h-full rounded-lg object-cover"
                            />
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Mobile products preview (visible on scroll) -->
            <div class="md:hidden mt-12 opacity-0 transition-opacity duration-500" id="mobile-products">
                <h2 class="text-2xl font-bold text-center mb-6 text-gray-800 dark:text-white">Nuestros Productos</h2>
                <div class="grid grid-cols-2 gap-4">
                    <div class="bg-white dark:bg-gray-800 rounded-xl shadow-md p-3 transform transition-transform hover:scale-105">
                        <img src="https://betsol-web.s3.us-east-2.amazonaws.com/florida-lottery.avif" alt="Florida Lottery" class="w-full h-auto rounded-lg">
                        <p class="text-center mt-2 font-medium text-gray-800 dark:text-white">Florida Lottery</p>
                    </div>
                    <div class="bg-white dark:bg-gray-800 rounded-xl shadow-md p-3 transform transition-transform hover:scale-105">
                        <img src="https://betsol-web.s3.us-east-2.amazonaws.com/LoteriaNacionalGORDITO.svg" alt="Gordito" class="w-full h-auto rounded-lg p-2">
                        <p class="text-center mt-2 font-medium text-gray-800 dark:text-white">Gordito</p>
                    </div>
                </div>
            </div>
        </AtomsContainer>
    </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const videoElement = ref(null);

// Function to handle video loading and caching
onMounted(() => {
    if (videoElement.value) {
        // Set cache control headers via fetch before loading the video
        const videoUrl = 'https://betsol-web.s3.us-east-2.amazonaws.com/lottery-animation.mp4';
        
        // Preload the video using fetch API to cache it
        fetch(videoUrl, {
            method: 'GET',
            headers: {
                'Cache-Control': 'max-age=31536000', // Cache for 1 year
            },
        })
        .then(response => {
            if (videoElement.value) {
                // Once preloaded, ensure video plays
                videoElement.value.play().catch(error => {
                    console.warn('Auto-play was prevented:', error);
                });
            }
        })
        .catch(error => {
            console.error('Failed to preload video:', error);
        });
    }
});
</script>

<style scoped>
/* Rainbow cursor trail */
.rainbow-particle {
    pointer-events: none;
    position: fixed;
    width: 4px;
    height: 4px;
    background: linear-gradient(124deg, #ff2400, #e81d1d, #e8b71d, #e3e81d, #1de840, #1ddde8, #2b1de8, #dd00f3, #dd00f3);
    border-radius: 50%;
    animation: rainbow-fade 1s linear forwards;
    z-index: 9999;
    box-shadow: 0 0 6px rgba(255, 255, 255, 0.8);
}

/* Floating animation for leprechaun */
@keyframes float {
    0%, 100% {
        transform: translateY(0) rotate(0deg);
    }
    25% {
        transform: translateY(-10px) rotate(-1deg);
    }
    50% {
        transform: translateY(0) rotate(0deg);
    }
    75% {
        transform: translateY(10px) rotate(1deg);
    }
}

/* Rainbow border animation */
.rainbow-border {
    position: absolute;
    inset: 0;
    border-radius: inherit;
    padding: 2px;
    background: linear-gradient(45deg, #ff0000, #ff9a00, #d0de21, #4fdc4a, #3fdad8, #2fc9e2, #1c7fee, #5f15f2, #ba0cf8, #fb07d9);
    -webkit-mask: 
        linear-gradient(#fff 0 0) content-box, 
        linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    opacity: 0;
    transition: opacity 0.3s ease;
    animation: border-rotate 4s linear infinite;
}

.absolute:hover .rainbow-border {
    opacity: 1;
}

@keyframes border-rotate {
    0% {
        background-position: 0% 50%;
    }
    100% {
        background-position: 130% 50%;
    }
}

@keyframes rainbow-fade {
    0% {
        transform: scale(1);
        opacity: 1;
    }
    100% {
        transform: scale(0);
        opacity: 0;
    }
}

/* Animated gradient text */
@keyframes gradient-x {
    0%, 100% {
        background-size: 200% 200%;
        background-position: left center;
    }
    50% {
        background-size: 200% 200%;
        background-position: right center;
    }
}

.animate-gradient-x {
    animation: gradient-x 3s ease infinite;
}

.animate-spin-slow {
    animation: spin 8s linear infinite;
}

.animate-pulse-slow {
    animation: pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
    0%, 100% {
        opacity: 0.3;
    }
    50% {
        opacity: 0.5;
    }
}

@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

/* Floating clovers */
.clover {
    position: absolute;
    width: 30px;
    height: 30px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%2343a047' opacity='0.3'%3E%3Cpath d='M12,2C9.8,2,8,3.8,8,6c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4C16,3.8,14.2,2,12,2z M12,8C10.9,8,10,7.1,10,6c0-1.1,0.9-2,2-2 s2,0.9,2,2C14,7.1,13.1,8,12,8z M12,10c-2.2,0-4,1.8-4,4c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4C16,11.8,14.2,10,12,10z M12,16 c-1.1,0-2-0.9-2-2c0-1.1,0.9-2,2-2s2,0.9,2,2C14,15.1,13.1,16,12,16z M18,12c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4c0-2.2-1.8-4-4-4 C19.8,8,18,9.8,18,12z M24,12c0,1.1-0.9,2-2,2s-2-0.9-2-2c0-1.1,0.9-2,2-2S24,10.9,24,12z M2,12c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4c0-2.2-1.8-4-4-4C3.8,8,2,9.8,2,12z M8,12 c0,1.1-0.9,2-2,2s-2-0.9-2-2c0-1.1,0.9-2,2-2S8,10.9,8,12z'/%3E%3C/svg%3E");
    background-size: contain;
    background-repeat: no-repeat;
    opacity: 0.5;
    animation: float-clover 15s ease-in-out infinite;
}

.clover-1 {
    top: 15%;
    left: 10%;
    animation-delay: 0s;
}

.clover-2 {
    top: 25%;
    right: 15%;
    animation-delay: -3s;
}

.clover-3 {
    bottom: 30%;
    left: 20%;
    animation-delay: -6s;
}

.clover-4 {
    bottom: 15%;
    right: 10%;
    animation-delay: -9s;
}

.clover-5 {
    top: 50%;
    left: 50%;
    animation-delay: -12s;
}

@keyframes float-clover {
    0%, 100% {
        transform: translateY(0) translateX(0) rotate(0deg);
    }
    25% {
        transform: translateY(-30px) translateX(15px) rotate(10deg);
    }
    50% {
        transform: translateY(0) translateX(30px) rotate(0deg);
    }
    75% {
        transform: translateY(30px) translateX(15px) rotate(-10deg);
    }
}

.rainbow-border {
    background: linear-gradient(90deg, #ff0000, #ff7f00, #ffff00, #00ff00, #0000ff, #4b0082, #8b00ff);
    background-size: 1400% 1400%;
    animation: rainbow 10s ease infinite;
}

@keyframes rainbow {
    0% {background-position: 0% 50%;}
    50% {background-position: 100% 50%;}
    100% {background-position: 0% 50%;}
}

.clover {
    position: absolute;
    width: 30px;
    height: 30px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%2344bd32' width='24px' height='24px'%3E%3Cpath d='M12,2C9.8,2,8,3.8,8,6c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4C16,3.8,14.2,2,12,2z M12,8c-1.1,0-2-0.9-2-2c0-1.1,0.9-2,2-2 s2,0.9,2,2C14,7.1,13.1,8,12,8z M12,10c-2.2,0-4,1.8-4,4c0,2.2,1.8,4,4,4c2.2,0,4-1.8,4-4C16,11.8,14.2,10,12,10z M12,16 c-1.1,0-2-0.9-2-2c0-1.1,0.9-2,2-2s2,0.9,2,2C14,15.1,13.1,16,12,16z M18,12c0-2.2-1.8-4-4-4v8C16.2,16,18,14.2,18,12z M6,12 c0,2.2,1.8,4,4,4V8C7.8,8,6,9.8,6,12z'/%3E%3C/svg%3E");
    background-size: contain;
    opacity: 0.7;
    z-index: 5;
}

.clover-1 {
    top: 20%;
    left: 20%;
    animation: float 8s ease-in-out infinite;
}

.clover-2 {
    top: 60%;
    left: 70%;
    animation: float 12s ease-in-out infinite 1s;
}

.clover-3 {
    top: 30%;
    left: 50%;
    animation: float 10s ease-in-out infinite 2s;
}

@keyframes float {
    0% {
        transform: translateY(0) rotate(0deg);
    }
    50% {
        transform: translateY(-20px) rotate(180deg);
    }
    100% {
        transform: translateY(0) rotate(360deg);
    }
}
</style>