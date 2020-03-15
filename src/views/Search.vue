<template>
  <div class="about">
    <Header />
    <SearchHero />

    <main class="py-4 px-4 sm:p-8 m-0 sm:m-8 mb-10">
      <div class="block flex flex-wrap md:-mx-2" v-if="result && result.length !== 0">
        <div class="w-full sm:w-1/3 px-2 sm:px-8 py-4" v-for="(meal ,key) in result" :key="key">
          <SearchCard :meal="meal" @view="handleModal($event)" />
        </div>
      </div>

      <div class="bg-white text-center" v-else>
        <NoData class="h-64 w-64 mx-auto" />
        <p class="capitalize">No Data for <u class="font-extrabold">{{ search }}</u></p>
      </div>
    </main>

    <Modal :active="modal" v-if="modal" @close="modal = $event">
      <ViewMeal :meal="selected" />
    </Modal>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import SearchHero from '@/components/SearchHero.vue'
import ViewMeal from '@/components/ViewMeal.vue'
import SearchCard from '@/Shared/SearchCard.vue'
import Modal from '@/Shared/Modal.vue'
import NoData from '@/Shared/NoData.vue'
import axios from "axios"

export default {
  name: "Search",
  components: {
    Header, SearchHero, SearchCard, Modal, ViewMeal, NoData
  },

  data(){
    return{
      result: [],
      modal: false,
      selected: {}
    }
  },

  computed:{
    search(){
      return this.$route.params.search
    }
  },

  watch: {
    $route(to, from) {
      this.searchMeals()
      this.modal = false
    }
  },

  methods: {
    searchMeals(){
      axios.get('https://www.themealdb.com/api/json/v1/1/search.php?s=' + this.search).then(n => this.result = n.data.meals);
    },

    handleModal(obj){
      this.selected = obj;
      this.modal = true;
    }
  },

  mounted(){
    this.searchMeals();
  }
}
</script>

<style>

</style>
