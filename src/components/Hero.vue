<template>
    <div class="absolute mt-0 py-0 w-full min-h-full bg-no-repeat bg-cover bg-center" style="background-image:url('https://images.unsplash.com/photo-1494253109108-2e30c049369b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80')">

        <section class="px-2 lg:px-0 mt-32 sm:mt-56 w-full container mx-auto pb-16">
            <div class="w-full text-white">
                <div class="w-full text-center">
                    <h2 class="leading-none font-bold text-2xl xs:text-2x1 md:text-5xl lg:6x1 capitalize">Cook Delicious & Healthy Meals with <span class="text-blue-400">the Best Recipes</span></h2>
                </div>
            </div>

            <div class="flex justify-center mt-16 sm:mt-10">
                <SearchBar />
            </div>

            <div class="text-center text-white mt-32">
                <p>Delicious Food To fit your lifestyle.</p>
            </div>
        </section>

    </div>

</template>

<script>
import Header from '@/components/Header.vue'
import SearchBar from '@/Shared/SearchBar'
export default {
    name: "Hero",
    components: { Header, SearchBar }
}
</script>

<style>

</style>
