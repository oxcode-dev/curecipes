<template>
  <div class="hello">
    <div class="flex items-center">
      <Logo class="w-20 h-10" />
      <span class="logo-text">curecipes</span>
    </div>
    <h1>{{ msg }}</h1>
<main class="py-4">
  <div class="px-4">
    <div class="block md:flex justify-between md:-mx-2">
      <div class="w-full lg:w-1/3 md:mx-2 mb-4 md:mb-0">
        <div class="bg-white rounded-lg overflow-hidden shadow relative">
          <img class="h-56 w-full object-cover object-center" src="https://images.unsplash.com/photo-1457282367193-e3b79e38f207?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1654&q=80" alt="">
          <div class="p-4 h-auto md:h-40 lg:h-48">
            <a href="#" class="block text-blue-500 hover:text-blue-600 font-semibold mb-2 text-lg md:text-base lg:text-lg">
              Woman standing under blue sky
            </a>
            <div class="text-gray-600 text-sm leading-relaxed block md:text-xs lg:text-sm">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo quidem blanditiis unde asperiores? Officia amet perspiciatis ad quibusdam incidunt eaque, nobis, eveniet neque porro id commodi quisquam debitis!
            </div>
            <div class="relative mt-2 lg:absolute bottom-0 mb-4 md:hidden lg:block">
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#something</a>
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#sky</a>
            </div>
          </div>
        </div>
      </div>
      <div class="w-full lg:w-1/3 md:mx-2 mb-4 md:mb-0">
        <div class="bg-white rounded-lg overflow-hidden shadow relative">
          <img class="h-56 w-full object-cover object-center" src="https://images.unsplash.com/photo-1465188162913-8fb5709d6d57?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60" alt="">
          <div class="p-4 h-auto md:h-40 lg:h-48">
            <a href="#" class="block text-blue-500 hover:text-blue-600 font-semibold mb-2 text-lg md:text-base lg:text-lg">
              Woman walking on pathway
            </a>
            <div class="text-gray-600 text-sm leading-relaxed block md:text-xs lg:text-sm">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Iure aut quia alias ullam eveniet sunt! Ipsa, sunt. Inventore ipsum sit quasi. Alias quasi officiis blanditiis!
            </div>
            <div class="relative mt-2 lg:absolute bottom-0 mb-4 md:hidden lg:block">
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#pathway</a>
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#woman</a>
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#walkalone</a>
            </div>
          </div>
        </div>
      </div>
      <div class="w-full lg:w-1/3 md:mx-2 mb-4 md:mb-0">
        <div class="bg-white rounded-lg overflow-hidden shadow relative">
          <img class="h-56 w-full object-cover object-center" src="https://images.unsplash.com/photo-1467238307002-480ffdd260f2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60" alt="">
          <div class="p-4 h-auto md:h-40 lg:h-48">
            <a href="#" class="block text-blue-500 hover:text-blue-600 font-semibold mb-2 text-lg md:text-base lg:text-lg">
              Walking through a forest in the afternoon
            </a>
            <div class="text-gray-600 text-sm leading-relaxed block md:text-xs lg:text-sm">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Commodi nemo magni saepe cumque error quia quae sint ducimus, maiores doloremque.
            </div>
            <div class="relative mt-2 lg:absolute bottom-0 mb-4 md:hidden lg:block">
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#forest</a>
              <a class="inline bg-gray-300 py-1 px-2 rounded-full text-xs lowercase text-gray-700" href="#">#walk</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</main>
  <pre class="text-left">{{ a }}</pre>
  </div>
</template>

<script>
import axios from "axios"
import Logo from "@/Shared/Logo"
export default {
  name: 'HelloWorld',
  components: {Logo},
  props: {
    msg: String
  },

  data(){
    return{
      a: {}
    }
  },

  methods:{
    x(){
      axios.get('https://www.themealdb.com/api/json/v1/1/search.php?s=potato').then(n => this.a = n);
    }
  },

  mounted(){
    this.x()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.logo-text{
  margin-left: -17px;
  margin-top: 3px;
  font-family: 'Pacifico', cursive;
  color: #9c503c;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
