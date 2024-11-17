<script setup>

import { faker } from '@faker-js/faker'



// const firstname = faker.person.firstName()

// const lastname = faker.person.lastName()
// const fullname = faker.person.fullName({ irstName: firstname, lastName: lastname })
// const job_title = faker.person.jobTitle()
// const bio = faker.lorem.lines(2)
// const username = faker.internet.userName({firstName: firstname, lastName: lastname}).toLowerCase()

const props = defineProps({

    employee: {
        type: Object, 
        required: true, 
        default: () => {
            return {


                _id: "6730f937d8e95423aa1b7f33",
                userName: "wolfgang",
                firstName: "Ryan",
                lastName: "Woods",
                title: "Student",
                quote: "Never look back.",
                __v: 0,


            }
        },
    },
})









</script>


<!--  -->

<template>
    <RouterLink :to="{name: 'CardDetails', params: {id: props.employee._id} }">
    <div class="border border-gray-500 rounded-lg shadow bg-gray-400 h-full">
        <img class="object-fill h-480 w-960" v-bind:src="faker.image.urlLoremFlickr({category: 'cats', height: 480, width: 960})" />
        <div class="p-4">
            <p class="mb-2 text-2xl font-bold">{{ props.employee.firstName}} {{ props.employee.lastName }}</p>
            <p class="mb-3 font-normal text-gray-800">{{ props.employee.title }}</p>
            <p class="mb-3 font-normal text-gray-800">{{ props.employee.quote }}</p>
        </div>
    </div>


    </RouterLink>
</template>






















