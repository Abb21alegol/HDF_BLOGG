<template>
<div class="w-screen h-screen">
<div class="w-1/2 h-auto mx-auto bg-gradient-to-r from-black via-red-800 to-black">
    <img class="justify-items-center border-2 border-gray-800 rounded-lg" :src="dish.image"/>
    <h1 class="text-5xl mb-8 text-white text-center items-center">{{dish.title}}</h1>
    <p class="mb-8 text-white justify-center text-center">{{dish.description}}</p>
    <nuxt-content :document="dish" class="text-white justify-center"></nuxt-content>
</div>
</div>
</template>
<script>
export default {
    async asyncData({$content, params}) {
        
        let dish = await $content('dishes/dish'+params.id).fetch()
        console.log(dish)

        return {
            dish
        }
    },
}
</script>
