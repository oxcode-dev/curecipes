<template>
    <div class="flex justify-center m-4 w-auto">
      <div class="w-full sm:w-1/3 rounded overflow-hidden shadow-lg my-2 bg-white">
        <img class="w-full" :src="meal.strMealThumb" alt="Sunset in the mountains">
        <div class="px-6 py-2">
            <div class="font-bold text-xl mb-2">{{ meal.strMeal }}t</div>
            <div class="text-grey-darker text-base">
                {{ meal.strInstructions }}
            </div>
            <div class="py-1">
                <h2 class="block text-sm font-bold">Category</h2>
                <span>{{ meal.strCategory }}</span>
            </div>
            <div class="py-1">
                <h2 class="block text-sm font-bold">Area</h2>
                <span>{{ meal.strArea }}</span>
            </div>
        </div>
        <div class="px-6 py-2">
            <div class="w-full">
                <h2 class="block text-sm font-bold">Ingredients & Measurements</h2>

                <div class="flex items-center" v-for="(ingredient, key) in ingredients" :key="key">
                    <div class="text-center py-1 px-2">
                        <p class="text-xl p-0 text-green-dark">&bull;</p>
                    </div>
                    <div class="w-4/5 py-1 px-1">
                        <span class="pr-2">{{ ingredient }}</span>
                        <span class="">- {{ measurements[key] }}</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="px-6 py-4">
            <router-link :to="link(meal.strCategory)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1">{{ meal.strCategory }}</router-link>
            <router-link :to="link(meal.strArea)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1">{{ meal.strArea }}</router-link>
            <router-link :to="link(tag)" class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700 mr-1" v-for="tag in tags" :key="tag" v-show="tag">{{ tag }}</router-link>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    name: "ViewMeal",
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
        },
        ingredients(){
            let arr = [];
           let cleanObj = Object.keys(this.meal).reduce((acc, key) => (this.meal[key] === undefined || this.meal[key] === null || this.meal[key] === '' ? acc : {...acc, [key]: this.meal[key]}), {})
           let keys = Object.keys(cleanObj).filter(a => a.includes('strIngredient'));
            for (const item in keys) {
                arr.push(cleanObj[keys[item]])
            }
           return arr
        },
        measurements(){
            let arr = [];
           let cleanObj = Object.keys(this.meal).reduce((acc, key) => (this.meal[key] === undefined || this.meal[key] === null || this.meal[key] === '' ? acc : {...acc, [key]: this.meal[key]}), {})
           let keys = Object.keys(cleanObj).filter(a => a.includes('strMeasure'));
            for (const item in keys) {
                arr.push(cleanObj[keys[item]])
            }
           return arr.slice(0, this.ingredients.length)
        }
    }
}
</script>

<style>

</style>
