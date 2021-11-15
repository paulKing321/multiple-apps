<template>
  <h1>Job Details Page</h1>
  <p>The job id is {{ id }} </p>
</template>

<script>
export default {
    props: ['id'],
    // i could use props in place of data function to pass in parameters, just declare props true in the router index.js registration

// data() {
    //     return {
    //         id: this.$route.params.id
    //     }
    // }
}
</script>

<style>

</style>