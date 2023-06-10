<template>
  <div>
    <div class="d-flex">
      <b-row>
        <b-col>
          <b-form-input
            v-model="filter"
            type="search"
            placeholder="Search"
          ></b-form-input>
        </b-col>
      </b-row>

      <b-button @click="filter" class="s_bt" md="3" variant="primary">Search</b-button>
    </div>
    
    <b-table class="bg" striped hover :items="users" :filter="filter"></b-table> 
    
  </div>
</template>

<script>
export default {
  props: ["users"],
  data: () => ({
    filter: "",
  }),

  //   data() {
  //     return {

  //       users: [],

  //     }
  //   },
  //   mounted() {
  //     fetch('http://localhost:3000/users')
  //       .then((res) => res.json())
  //       .then( data => this.users = data)
  //       .catch( err => console.log(err.message))

  //   },
  //   methods:{
  //     MyFunctin(){
  //         this.users = this.users.phone.join();
  //     }
  //   }
};
</script>

<style scoped>
.table {
  margin-top: 2rem;
}

.s_bt{
    margin-left: 1rem;
    width: 6rem;
}

</style>
