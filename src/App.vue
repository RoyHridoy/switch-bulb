<script setup>
import { reactive } from 'vue';
const lights = reactive([1, 0, 0])

const lightImage = {
    on: 'on.png',
    off: 'off.png'
}

</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Switching Bulb</h1>
        <p class="p-5">Click the switch to on off the bulb</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5 justify-between">

                <button v-for="(light, index) in lights" :key="light" :class="1 == light ? 'bg-blue-500' : 'bg-gray-500'"
                    @click="lights[index] = !lights[index]"
                    class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    {{ light == 1 ? `Light ${index + 1} On` : `Light ${index + 1} Off` }}
                </button>

            </div>
            <div class="border w-96 flex flex-col space-y-5 px-10 py-5">
                <img v-for="light in lights" :key="light" class="w-20" :src="light ? lightImage.on : lightImage.off" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped>

</style>
