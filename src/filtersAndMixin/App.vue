<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                <p>{{text | toUppercase | to-lowercase}}</p>
                <button @click="fruits.push('berries')">add new item</button>
                <input v-model="filterText">
                <ul>
                  <li v-for="fruit in filteredFruits">{{fruit}}</li>
                </ul>
                <hr>
                <app-list></app-list>
            </div>
        </div>
    </div>
</template>

<script>
import List from './List.vue'
import {fruitMixin} from './fruitMixin'
    export default {
      mixins: [fruitMixin],
      data(){
        return{
          text: 'hello there',

        }
      },
      filters: {
        toUppercase(value){
          return value.toUpperCase()
        }
      },
      computed: {
        filteredFruits(){
          return this.fruits.filter((el)=>{
            return el.match(this.filterText);
          })
        }
      },
      components: {
        appList: List
      }
    }
</script>

<style>

</style>
