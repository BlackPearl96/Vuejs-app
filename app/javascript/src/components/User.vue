<template>
  <div class="component">
    <p>Ten toi la {{ name }}</p>
    <p>Toi nam nay {{ age }} tuoi</p>
    <hr />
    <div class="row">
      <div class="col-xs-12 col-sm-6 col-6">
        <app-user-detail v-bind:age="age" @ageWasUpdated="age = $event ">
        </app-user-detail>
      </div>
      <div class="col-xs-12 col-sm-6 col-6">
        <app-user-edit v-bind:user-age="age" @ageWasEdited="age = $event">
          </app-user-edit>
      </div>
      <button @click="resetAge">Reset Tuoi</button>
    </div>
  </div>
</template>

<script>
import UserDetail from "./UserDetail.vue";
import UserEdit from "./UserEdit.vue";

export default {
  data: function() {
    return {
      name: "Charlie",
      age: 23
    };
  },
  methods:{
    resetAge: function(){
      this.age = 23
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit
  }
};
</script>
