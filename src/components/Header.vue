<template>
    <header class="p-4 absolute w-full top-0 z-50">
        <div class="flex justify-between mx-1 sm:mx-8 items-center">
             <router-link to="/" class="flex items-center">
                <Logo class="w-20 h-10" />
                <span class="logo-text">curecipes</span>
             </router-link>
            <div class="lg:flex text-white">
                <ul class="flex align-items-center pt-2">
                    <li class="ml-4 p4"><a href="https://github.com/codeosemeke/curecipes" target="blank">Github</a></li>
                </ul>
            </div>
        </div>
    </header>
</template>

<script>
import Logo from "@/Shared/Logo"
export default {
    name: "Header",
    components:{ Logo }
}
</script>

<style>

</style>
