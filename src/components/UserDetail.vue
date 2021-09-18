<template>
<div>
  <h2>you may view the user details here</h2>
  <p>many details</p>
  <p>user name {{switchName()}}</p>
  <p>user age {{userAge}}</p>
  <button @click="resetName()">reset name</button>
</div>
</template>

<script>
  export default{
    props:{
      name: String,
      userAge: Number,
    },
    methods: {
      switchName(){
        return this.name.split("").reverse().join("");
      },
      resetName(){
        this.name ='salome';
        this.$emit('nameWasReset', this.name)
      }
    },
  }
</script>

<style scoped>
div{
  background: indianred;
}
</style>
