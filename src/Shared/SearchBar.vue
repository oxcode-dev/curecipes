<template>
    <form class="text-gray-600 flex bg-white w-5/6 sm:w-3/5 py-2 px-4 rounded" @submit.prevent="submit">
        <input type="search" v-model="search" placeholder="Search" class="bg-white w-full h-10 px-2 border-gray-400 border mr-2 rounded text-sm focus:outline-none">
        <button type="submit" class="flex items-center text-white bg-blue-600 p-2 rounded">
            <svg class="h-4 mr-2 w-4 fill-current" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" id="Capa_1" x="0px" y="0px" viewBox="0 0 56.966 56.966" style="enable-background:new 0 0 56.966 56.966;" xml:space="preserve" width="512px" height="512px">
            <path d="M55.146,51.887L41.588,37.786c3.486-4.144,5.396-9.358,5.396-14.786c0-12.682-10.318-23-23-23s-23,10.318-23,23  s10.318,23,23,23c4.761,0,9.298-1.436,13.177-4.162l13.661,14.208c0.571,0.593,1.339,0.92,2.162,0.92  c0.779,0,1.518-0.297,2.079-0.837C56.255,54.982,56.293,53.08,55.146,51.887z M23.984,6c9.374,0,17,7.626,17,17s-7.626,17-17,17  s-17-7.626-17-17S14.61,6,23.984,6z"/>
            </svg>
            Search
        </button>
    </form>
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return{
            search: null
        }
    },

    watch: {
    $route(to, from) {
      this.search = this.$route.params.search ? this.$route.params.search : null
    }
  },

    methods:{
        submit(){
            if(this.search !== this.$route.params.search){
                this.$router.push({ name: 'Search', params: { search: this.search } })
            }
        }
    },

    mounted(){
        this.search = this.$route.params.search ? this.$route.params.search : null
    }
}
</script>

<style>

</style>
