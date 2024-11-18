<script setup>


import { useRoute } from 'vue-router'
import {ref, onMounted, onUnmounted} from 'vue' 
import useAPI from '@/composables/useAPI';
import { faker } from '@faker-js/faker'

const { fetchEmployee, currentEmployee } = useAPI()


onMounted(async () => {
    await fetchEmployee(Route.params.id)
})





onUnmounted(() => {
    currentEmployee.value = null
})


const route = useRoute()










</script>





<template>




<div class="border border-gray-400 rounded-lg shadow bg-gray200 h-full">
 <img :src="faker.image.urlLoremFlickr({width: 640, height: 480, category: 'person'})" class="rounded-t-xl mx-auto object-center"/>


 <main>
    <div v-if="currentEmployee" class ="flex flex-col items-center justify-center gap-6 ">



        <h1 class="mb-2 text-6xl font-bold p-5">{{ currentEmployee.firstName }} {{ currentEmployee.lastName }}</h1>
        <h1 class="mb-2 text 2xl font-thin font-italics p-5"> "{{currentEmployee.quote}}" </h1>



        <p class="mx-auto">
            <h1 class="mb-2 text 3x1 p-5">{{ currentEmployee.title }}</h1>
            <h1 class="mb-2 text 2xl p-5">{{ currentEmployee.userName }}</h1>
        </p>

    </div>
 </main>

</div>




</template>