<template>
  <div>
      <h1> {{title}} </h1>
      <NLink to="/"> Home </NLink>
  </div>
</template>

<script>
export default {
    // middleware: 'test',
    asyncData(){
        return{
            title: 'About'
        }

    },
    head(){
        return{
            title: 'About',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'My amazing about page'
                }
            ],
            script:[
                {
                    src: '/about.js'
                }
            ]
        }
    }

}
</script>

<style>

</style>