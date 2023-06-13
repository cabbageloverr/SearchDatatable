<template>
  <div>
    <div class="d-flex">
      <b-row>
        <b-col>
          <b-form-input
            v-model="text"
            type="text"
            placeholder="Search"
          ></b-form-input>
        </b-col>
      </b-row>

      <b-button @click="text" class="s_bt" md="3" variant="primary"
        >Search</b-button
      >
    </div>
    <h3 class="result">
      Result <span class="text_gray">({{ userlist.length }})</span>
    </h3>
    <!-- {{ userlist }} -->
    <b-table class="bg" hover responsive="m" :fields="fields" :items="userlist">
      <template #cell(phones)="data">
        <template v-for="phone in data.item.phones">
          <div :key="phone" class="border">{{ phone }}</div>
        </template>
        <!-- {{ data.item.phones.join() }} -->
      </template>
    </b-table>
    <!-- ขอเก็ยไว้ดูนะจ๊ะ -->
    <!-- <MyBox>
      <template v-slot:content1>
        <b-button>content1</b-button>
      </template>
      <template #:content2="dddd">
        <b-button>{{ dddd }}</b-button>
      </template>
    </MyBox>
    <MyBox :border="true"><b-button></b-button></MyBox>
    <BCard><b-button></b-button></BCard> -->
  </div>
</template>

<script>
// import MyBox from "./MyBox.vue";
// import { BCard } from 'bootstrap-vue';
export default {
  props: ["users"],
  // components: {
  //   MyBox: MyBox,
  //   // BCard
  // },
  data: () => ({
    result: [],
    text: "",
    fields: [
      "name",
      // A regular column
      { key: "phones", label: "phones" },
      // A regular column
      "email",
    ],
  }),
  computed: {
    userlist() {
      return this.search()
    },
  },
  methods: {
    search() {
      return this.users.filter(
        (item) =>
          this.findInArr(item.phones, this.text) ||
          item.name.toLowerCase().includes(this.text.toLowerCase()) ||
          item.email.toLowerCase().includes(this.text.toLowerCase())
      );
    },
    findInArr(array, keyword) {
      //some()
      for (let i = 0; i < array.length; i++) {
        const item = array[i];
        if (item.startsWith(keyword)) {
          return true;
        }
      }
      return false;
    },
  },
};

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
//         this.users = this.users.phone;
//     }
//   }
</script>

<style>
.table {
  margin-top: 2rem;
}

.s_bt {
  margin-left: 1rem;
  width: 10rem;
  background-color: rgb(89, 13, 204) !important;
}

.s_bt:hover {
  background-color: rgb(135, 108, 230) !important;
}

.result {
  margin-top: 1rem;
}

th {
  background-color: rgb(233, 232, 241) !important ;
}

.text_gray {
  color: rgb(165, 172, 178);
}
</style>
