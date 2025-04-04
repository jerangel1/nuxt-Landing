<template>
  <section class="pt-20 md:pt-24">
    <AtomsContainer>
      <div class="grid md:grid-cols-2 gap-10 xl:gap-14 relative">
        <div class="md:py-2 lg:py-4 relative">
          <div class="absolute left-0 top-0 h-full w-full flex justify-end">
            <span class="flex opacity-20">
              <span
                class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"
              ></span>
              <span
                class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"
              ></span>
            </span>
          </div>
          <div class="relative">
            <AtomsTitle texte="¿Por qué Pronosticon es Diferente?" />
            <p class="text-gray-600 dark:text-gray-300 pt-8">
              Pronosticon no es solo otra plataforma de lotería. Somos tu
              compañero confiable para mantenerte informado, analizar tendencias
              y maximizar tus posibilidades.
            </p>
            <div class="space-y-4 pt-8">
              <div
                class="p-4 rounded-xl border border-box-border transition hover:bg-gray-200 dark:hover:bg-box-bg"
              >
                <h3
                  class="text-gray-700 dark:text-gray-200 font-semibold text-xl"
                >
                  Resultados Instantáneos
                </h3>
                <p class="text-base text-gray-600 dark:text-gray-300">
                  Recibe notificaciones en tiempo real de todos los sorteos
                  importantes.
                </p>
              </div>
              <div
                class="p-4 rounded-xl border border-box-border transition hover:bg-gray-200 dark:hover:bg-box-bg"
              >
                <h3
                  class="text-gray-700 dark:text-gray-200 font-semibold text-xl"
                >
                  Análisis de Probabilidades
                </h3>
                <p class="text-base text-gray-600 dark:text-gray-300">
                  Estadísticas avanzadas y pronósticos basados en datos
                  históricos.
                </p>
              </div>
              <div
                class="p-4 rounded-xl border border-box-border transition hover:bg-gray-200 dark:hover:bg-box-bg"
              >
                <h3
                  class="text-gray-700 dark:text-gray-200 font-semibold text-xl"
                >
                  Múltiples Loterías
                </h3>
                <p class="text-base text-gray-600 dark:text-gray-300">
                  Seguimiento de resultados para diversas loterías nacionales e
                  internacionales.
                </p>
              </div>
            </div>
            <div class="pt-10 flex">
              <AtomsLinkBtn href="/registro" variant="primary">
                Comenzar Ahora
              </AtomsLinkBtn>
            </div>
          </div>
        </div>
        <div class="flex md:h-full relative">
          <div
            class="absolute z-0 top-1/2 -translate-y-1/2 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-primary to-pink-300 dark:from-[#570cac] dark:to-primary blur-2xl"
          ></div>
          <div
            class="w-full h-[27rem] sm:h-[30rem] md:h-full flex justify-start md:justify-end relative pb-5"
          >
            <!-- <img
              src="https://betsol-web.s3.us-east-2.amazonaws.com/duende/2.png"
              alt="Resultados de Lotería"
              width="300"
              class="w-2/5 aspect-square absolute bottom-0 right-0 md:left-0 object-cover rounded-t-[30%] rounded-b-[30%] border-4 border-box-border shadow-md shadow-box-shadow"
            /> -->
            <img
              src="https://betsol-web.s3.us-east-2.amazonaws.com/duende/1.png"
              alt="Análisis de Lotería"
              width="500"
              class="w-11/12 lg:w-5/6 h-full object-cover rounded-t-[10rem] rounded-b-[10rem] md:rounded-t-[11rem] md:rounded-b-[11rem] lg:rounded-t-[14rem] lg:rounded-b-[14rem]"
            />
          </div>
        </div>
      </div>
    </AtomsContainer>
  </section>
</template>

<script lang="ts" setup>
// No additional logic needed for this component
</script>

<style scoped>
/* Optional: Add any specific styling for this component */
</style>
