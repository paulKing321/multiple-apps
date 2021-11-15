<template>
<div class="m-auto w-full flex justify-between" style="justify-content: center">
  <div class="">
    <h1 class="text-2xl mt-5">DC HEROS {{herosCount}}</h1>

    <ul>
      <li class="flex pt-4 pl-4 pr-4 justify-between" v-for="(hero, index) in dcHeros" :key="hero.name">
        <div>
          {{ hero.name }}
        </div>
        <button class="bg-gradient-to-t from-red-700 to-blue-200 px-2 py-1" @click="remove(index)">x</button>
      </li>
    </ul>
  
    <form class="my-10 flex mx-2 justify-between" @submit.prevent="addHero"> 
      <!-- submit.prevent stops the default action of the submit -->
      <input class="border rounded" placeholder="Type Hero Name Here" v-model="newHero"/>
      <!-- v-model.trim removes white spaces -->
      <!-- v.model.lazy only update the data you input once the user looses focus on the textarea,input.. -->
      <!-- v.model.number if for numbers -->
      <!-- <button   @click="alert">Add Hero</button> -->
      <button class="border rounded bg-gradient-to-t from-red-700 to-pink-500 text-white" type="submit" v-if="newHero == ''" onclick="alert('oga input jorr!!')">Add Hero</button>
      <!-- this above is for an alert pop up, javascript -->
    </form>
  </div>
</div>
</template>

<script>
export default {
  name: 'dcHeros',

  computed: {
    herosCount() {
      return this.dcHeros.length
    },
  },
  data() {
    return {
      // isDisabled: true,
      newHero: "",
      dcHeros: [
        {name: "Supergirl"},
        {name: "Flash"},
        {name:  "Arrow"}, 
        {name: "Batman"}, 
        {name: "Superman"},
      ],
      alert: "Oga Input Jorr!!",
    }
  },

  methods: {
    addHero() {
      if(this.newHero != '') {
      this.dcHeros.push({ name: this.newHero});
      // unshift instead of push will add the new item to the top
      this.newHero = '';
      }
    },
    remove(index) {
      this.dcHeros = this.dcHeros.filter((hero,i) => i != index); 
    },
  },
  }
</script>

<style>
/* .heros{
  margin: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.heros h1 {
  font-weight: 900;
} */

</style>