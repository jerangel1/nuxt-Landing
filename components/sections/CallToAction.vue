<template>
    <section class="py-20">
        <AtomsContainer>
            <div
                class="w-full relative py-8 md:py-10 px-6 md:px-8 rounded-2xl bg-gradient-to-tr from-gray-100 to-gray-200 dark:from-gray-900 dark:to-body-color">
                <div class="absolute right-0 top-0 h-full w-full flex justify-end">
                    <span class="flex opacity-20">
                        <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                        <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
                    </span>
                </div>

                <div class="absolute left-0 bottom-0 h-full w-full flex items-end">
                    <span class="flex opacity-20">
                        <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                        <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
                    </span>
                </div>
                <div class="mx-auto text-center max-w-xl md:max-w-2xl relative">
                    <h2 class="text-gray-800 pt-4 dark:text-white font-bold text-4xl md:text-5xl lg:text-6xl">
                        Recibe los <span
                            class="text-transparent bg-clip-text bg-gradient-to-br from-primary to-[#8cd66a]">Resultados</span>
                        del Día
                    </h2>
                    <p class="text-gray-600 dark:text-gray-300 pt-8 mx-auto max-w-xl">
                        ¡Suscríbete y sé el primero en conocer los resultados de tus loterías favoritas! Notificaciones directas a tu correo electrónico.
                    </p>
                    <div class="mx-auto max-w-md sm:max-w-xl pt-10">
                        <form @submit.prevent="subscribeToResults" class="flex items-center relative gap-x-2">
                            <input 
                                v-model="emailInput"
                                type="email" 
                                placeholder="tucorreo@ejemplo.com"
                                required
                                class="outline-none border-2 border-transparent focus:border-primary bg-body text-gray-600 dark:text-gray-200 rounded-3xl px-6 py-3 w-full"
                            >
                            <div
                                class="sm:inline-flex sm:min-w-max absolute sm:relative top-0.5 right-0.5 sm:top-0 sm:right-0">
                                <button
                                    type="submit"
                                    class="min-w-max p-3 sm:py-3 sm:px-6 text-white border-2 border-transparent relative group">
                                    <span
                                        class="absolute inset-0 rounded-full group-hover:scale-105 origin-center transition-all ease-in-out bg-primary"></span>
                                    <span aria-hidden="true" class="relative hidden sm:flex">
                                        Suscribirse
                                    </span>
                                    <span class="relative flex sm:hidden">
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                            stroke-width="1.5" stroke="currentColor" class="w-5 h-5">
                                            <path stroke-linecap="round" stroke-linejoin="round"
                                                d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5" />
                                        </svg>
                                    </span>
                                </button>
                            </div>
                        </form>
                        <p v-if="subscriptionMessage" 
                           :class="subscriptionSuccess ? 'text-green-600' : 'text-red-600'"
                           class="mt-2 text-sm text-center">
                            {{ subscriptionMessage }}
                        </p>
                    </div>
                </div>
            </div>
        </AtomsContainer>
    </section>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const emailInput = ref('')
const subscriptionMessage = ref('')
const subscriptionSuccess = ref(false)

async function subscribeToResults() {
    try {
        // TODO: Implement actual email subscription logic
        // This could be an API call to your backend
        const response = await fetch('/api/subscribe', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify({ email: emailInput.value })
        })

        if (response.ok) {
            subscriptionSuccess.value = true
            subscriptionMessage.value = '¡Suscripción exitosa! Pronto recibirás resultados de lotería.'
            emailInput.value = '' // Clear input after successful subscription
        } else {
            throw new Error('Error en la suscripción')
        }
    } catch (error) {
        subscriptionSuccess.value = false
        subscriptionMessage.value = 'No se pudo completar la suscripción. Intenta de nuevo.'
    }
}
</script>

<style scoped>
/* Optional: Add some additional styling for the form */
input:focus {
    box-shadow: 0 0 0 2px rgba(var(--color-primary-rgb), 0.2);
}
</style>