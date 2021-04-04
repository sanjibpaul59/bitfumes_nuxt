<template>
  <div>
     <h1> {{slug.blog}} </h1>
  </div>
</template>

<script>
export default {
  validate({params}){
    return /^\d+$/.test(params.blog);
  },
  data(){
    return{
      slug: this.$route.params,
    }
  },
  created(){
    // console.log(this.$route.params);
  }

}
</script>

<style>

</style>