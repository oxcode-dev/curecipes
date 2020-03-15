<template>
    <div>
        <div class="mt-0 py-0 w-full bg-no-repeat bg-cover bg-center bg-blue-500">

            <section class="px-2 lg:px-0 w-full container mx-auto pb-16">
                <div class="w-full text-white pt-24">
                    <div class="w-full text-center">
                        <h2 class="leading-none font-bold text-2xl xs:text-2x1 md:text-5xl lg:6x1 capitalize">Search For
                            <span class="text-blue-400">{{ $route.params.search }}</span>
                        </h2>
                    </div>
                </div>

                <div class="flex justify-center mt-16 sm:mt-10">
                    <SearchBar />
                </div>
            </section>

        </div>
    </div>
</template>

<script>
import SearchBar from '@/Shared/SearchBar'
export default {
    name: "SearchHero",
    components: { SearchBar}
}
</script>

<style>

</style>
