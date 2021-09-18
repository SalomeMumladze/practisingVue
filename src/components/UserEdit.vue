<template>
<div>
  <h2>you may edit the user here</h2>
  <p>edit me!</p>
  <p>user age {{userAge}}</p>
  <button @click="editAge">edit age</button>
</div>
</template>


<script>
export default{
  methods: {
    props: ['userAge'],
    editAge(){
      this.age = 21
    }
  }
}

</script>


<style scoped>
div{
  background: green
}
</style>
