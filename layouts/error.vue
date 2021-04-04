<template>
  <div>
    <h3>This is error Page</h3>
    <h4> {{error.statusCode}} Not Found </h4>
  </div>
</template>

<script>
export default {
  layout: 'errorLayout',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  head () {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>
