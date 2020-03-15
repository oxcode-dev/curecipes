<template>
    <div class="bg-white rounded-lg overflow-hidden shadow relative">
        <img class="h-56 w-full object-cover object-center" :src="meal.strMealThumb" alt="">
        <div class="p-4 h-auto sm:h-30">
            <a href="#" @click.prevent="handleViewMeal" class="block text-blue-500 hover:text-blue-600 font-semibold mb-2 text-lg md:text-base lg:text-lg">
                {{ meal.strMeal }}
            </a>
            <div class="text-gray-600 text-sm leading-relaxed block md:text-xs lg:text-sm truncate">
                {{ meal.strInstructions }}
            </div>
            <div class="mt-2 mb-4">
                <router-link :to="link(meal.strCategory)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1">{{ meal.strCategory }}</router-link>
                <router-link :to="link(meal.strArea)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1">{{ meal.strArea }}</router-link>
                <router-link :to="link(tag)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1" v-for="tag in tags" :key="tag" v-show="tag">{{ tag }}</router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SearchCard',
    props: {
        meal:{
            type: Object,
            required: true
        }
    },

    methods:{
        link(search){
            return '/search/' + search.toLowerCase()
        },

        handleViewMeal(){
            this.$emit('view', this.meal)
        }
    },

    computed:{
        tags(){
            if(this.meal.strTags){
                return this.meal.strTags.split(',');
            }
        }
    }
}
</script>

<style>

</style>
