<template>
  <div>
    <h1>the user component</h1>
    <button @click="changeName">change my name</button>
    <p>name is {{name}}</p>
    <hr>
    <div class="component">
    <div>
      <app-user-detail
        :name="name"
        @nameWasReset="name = $event"
        :userAge="age">
      </app-user-detail>
    </div>
    <div>
      <app-user-edit :userAge="age"></app-user-edit>
    </div>
    </div>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue';
import UserEdit from './UserEdit.vue';

export default {
  data: function() {
    return{
      name: 'salome',
      age: 39
    }
  },
  methods:{
    changeName(){
      this.name = 'alexsi'
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit
  }
}

</script>

<style scoped>
.component{
  display: flex;
  justify-content: space-between;
}

</style>
