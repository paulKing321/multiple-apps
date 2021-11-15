<template>
<div class="flex flex-wrap w-full"> 
    <h1 class="w-full text-center text-3xl my-4">Markdown App</h1>
  <section class="flex m-auto w-10/12 w-full h-screen">
      <article class="w-1/2 border">
        <textarea class="w-full h-full" v-model="text"></textarea>
      </article>
      <article class="w-1/2 border bg-gray-400">{{ text }}</article>
  </section>
</div>
</template>

<script>
export default {
name: 'Markdown',

data() {
    return {
        text: "",

    }
}

}
</script>

<style>

</style>