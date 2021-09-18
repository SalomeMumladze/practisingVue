<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <button @click="selectComponent='appQuote'">Quote</button>
        <button @click="selectComponent='appAutor'">Author</button>
        <button @click="selectComponent='appNew'">New</button>
        <p>{{selectComponent}}</p>
        <keep-alive>
          <!-- this keep-alive tag kept alive this components not destroied-->
          <component :is="selectComponent">
            <p>default component</p>
          </component>
        </keep-alive>
        <!-- <app-quote>
          <p slot="title">hello</p>
          <h2 slot="subTitle">{{quoteTitle}}</h2>
        </app-quote> -->
      </div>
    </div>
  </div>
</template>

<script>
import Quote from './components/Quote.vue'
import Author from './components/Author.vue'
import New from './components/New.vue'
  export default {
    data: function(){
      return {
        quoteTitle: "wonderfull title",
        selectComponent: 'appQuote'
      }
    },
    components: {
      appQuote: Quote,
      appNew: New,
      appAutor: Author
    }
  }
</script>
