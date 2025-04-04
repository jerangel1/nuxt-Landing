<template>
    <section class="pt-20 md:pt-24 relative opacity-0 translate-y-10 transition-all duration-700" ref="sorteoSection">
        <AtomsContainer>
            <div class="flex justify-between items-center pb-6">
                <div class="">
                    <AtomsTitle texte="Categorías de Lotería" />
                </div>
                <div class="flex items-center min-w-max relative">
                    <AtomsLinkBtn href="/categorias" variant="primary">
                        Ver Todas
                    </AtomsLinkBtn>
                </div>
            </div>
            <div class="relative">
                <div 
                    class="flex absolute top-1/2 -left-5 -translate-y-1/2 z-10 transition duration-300 ease-linear" 
                    :class="prevIsVisible?'visible opacity-100':'invisible opacity-0'">
                    <AtomsSwiperNavButton @click="scrollToLeft()">
                        <IconsPrevIco />
                    </AtomsSwiperNavButton>
                </div>
                <div  
                    class="flex absolute top-1/2 -right-5 -translate-y-1/2 z-10 transition duration-300 ease-linear" 
                    :class="nextIsVisible?'visible opacity-100':'invisible opacity-0'">
                    <AtomsSwiperNavButton @click="scrollToRight()">
                        <IconsNextIco />
                    </AtomsSwiperNavButton>
                </div>

                <div data-slide-recent @scroll="initScroll()"
                    class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 py-4">
                    <div v-for="(item, index) in 4" :key="index" class="w-full opacity-0 translate-y-10" :class="['card-animation', `delay-${index}`]">
                        <div class="relative group bg-white dark:bg-gray-800 rounded-2xl shadow-xl overflow-hidden transform transition-all duration-300 hover:scale-[1.02] hover:shadow-2xl">
                            <div class="aspect-[4/3] overflow-hidden">
                                <img 
                                    :src="lotteryItems[index].image" 
                                    :alt="lotteryItems[index].title" 
                                    class="w-full h-full object-cover transform transition-transform duration-500 group-hover:scale-110"
                                    :class="{'object-contain p-4': lotteryItems[index].useContain}"
                                />
                            </div>
                            <div class="p-6">
                                <h3 class="text-xl font-bold text-gray-800 dark:text-white mb-2">{{ lotteryItems[index].title }}</h3>
                                <p class="text-gray-600 dark:text-gray-300 text-sm">{{ lotteryItems[index].description }}</p>
                                <div class="mt-4 flex justify-end">
                                    <button class="bg-primary/10 text-primary hover:bg-primary hover:text-white transition-colors duration-300 px-4 py-2 rounded-lg text-sm font-medium">
                                        Ver Resultados
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </AtomsContainer>
    </section>
</template>

<script setup lang="ts">
import { ref, onMounted, reactive } from 'vue';

const nextIsVisible = ref(false);
const prevIsVisible = ref(false);
const sorteoSection = ref<HTMLElement | null>(null);

const lotteryItems = reactive([
    {
        title: "Florida Lottery",
        description: "La lotería de Florida",
        image: "https://betsol-web.s3.us-east-2.amazonaws.com/florida-lottery.avif",
        useContain: false
    },
    {
        title: "Gordito",
        description: "La Lotería Nacional",
        image: "https://betsol-web.s3.us-east-2.amazonaws.com/LoteriaNacionalGORDITO.svg",
        useContain: true
    },
    {
        title: "Lotería Nacional",
        description: "Sorteos tradicionales y especiales",
        image: "https://betsol-web.s3.us-east-2.amazonaws.com/nacional.avif",
        useContain: false
    },
    {
        title: "Tres Monazos",
        description: "Sorteos diarios con grandes premios",
        image: "https://betsol-web.s3.us-east-2.amazonaws.com/tresMonazos.avif",
        useContain: false
    }
]);

let element: HTMLDivElement | null = null;

// Check if element is in viewport
const isInViewport = (element: HTMLElement | null): boolean => {
    if (!element) return false;
    const rect = element.getBoundingClientRect();
    return (
        rect.top <= (window.innerHeight || document.documentElement.clientHeight) * 0.8
    );
};

// Handle scroll event to show section when scrolled to
const handleScroll = () => {
    if (sorteoSection.value && isInViewport(sorteoSection.value)) {
        sorteoSection.value.classList.add('opacity-100');
        sorteoSection.value.classList.remove('translate-y-10');
        
        // Animate cards with staggered delay
        const cards = document.querySelectorAll('.card-animation');
        cards.forEach((card, index) => {
            setTimeout(() => {
                card.classList.add('animate-card');
            }, 150 * index);
        });
        
        // Remove event listener once animation is triggered
        window.removeEventListener('scroll', handleScroll);
    }
};

onMounted(() => {
    if (typeof document !== "undefined") {
        element = document.querySelector("[data-slide-recent]") as HTMLDivElement;
        initScroll();
    }
    
    // Add scroll event listener
    window.addEventListener('scroll', handleScroll);
    
    // Check if already in viewport on load
    setTimeout(() => {
        handleScroll();
    }, 100);
    
    return () => {
        if (element) {
            element.removeEventListener("scroll", initScroll);
        }
        window.removeEventListener('scroll', handleScroll);
    };
});

function initScroll(): void {
    if (typeof element === "undefined" || element === null) {
        return;
    }

    prevIsVisible.value = element.scrollLeft > 0;
    nextIsVisible.value = element.scrollLeft < element.scrollWidth - element.offsetWidth - 1;
}

function scrollToLeft(): void {
    if (typeof element === "undefined" || element === null) {
        return;
    }
    element.scrollLeft -= element.clientWidth;
    initScroll();
}

function scrollToRight(): void {
    if (typeof element === "undefined" || element === null) {
        return;
    }
    element.scrollLeft += element.clientWidth;
    initScroll();
}
</script>

<style scoped>
.invisible-scroll {
    scrollbar-width: none;
    -ms-overflow-style: none;
}
.invisible-scroll::-webkit-scrollbar {
    display: none;
}

.card-animation {
    transition: all 0.7s cubic-bezier(0.23, 1, 0.32, 1);
}

.animate-card {
    opacity: 1 !important;
    transform: translateY(0) !important;
}

.delay-0 { transition-delay: 0.1s; }
.delay-1 { transition-delay: 0.2s; }
.delay-2 { transition-delay: 0.3s; }
.delay-3 { transition-delay: 0.4s; }
</style>