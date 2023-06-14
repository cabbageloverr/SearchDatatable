<template>
  <CardStyle class="container con1">
    <div class="d-flex">
      <b-row>
        <b-col>
          <b-form-input
            v-model="text"
            type="text"
            placeholder="Search"
            :result="true"
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

    <div class="row gap-4">
      <CardUser
        :user="user"
        v-for="user in userlist"
        :key="user.name"
        class="col-3 user-table "
      >
      </CardUser>
    </div>
  </CardStyle>
</template>

<script>
import CardStyle from "./CardStyle.vue";
import CardUser from "./CardUser.vue";
// import { BCard } from 'bootstrap-vue';
export default {
  props: ["users"],
  components: {
    CardUser,
    CardStyle,
  },
  data: () => ({
    userlist: [],
    text: "",
    fields: [
      "name",
      // A regular column
      { key: "phones", label: "phones" },
      // A regular column
      "email",
    ],
  }),
  watch: {
    text: {
      handler() {
        this.userlist = this.search();
      },
      immediate: true,
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
      for (let i = 0; i < array.length; i++) {
        const item = array[i];
        if (item.startsWith(keyword)) {
          return true;
        }
      }
      return false;
    },
    mounted: function () {
      this.search();
    },
  },
};
</script>

<style>
.con1 {
  position: absolute;
  width: 1096px;
  height: auto;
  left: 5%;
  top: 86px;
  background: #ffffff;
  box-shadow: 1px 1px 6px rgba(69, 73, 87, 0.12);
  border-radius: 8px;
  padding: 24px !important;
}

.s_bt {
  margin-left: 3rem;
  width: 10rem;
  background-color: rgb(89, 13, 204) !important;
}

.s_bt:hover {
  background-color: rgb(135, 108, 230) !important;
}

.result {
  margin-top: 1rem;
  font-weight: bold;
}

/* th {
  background-color: rgb(233, 232, 241) !important ;
} */

.row{
  margin-left: 0 !important;
}
.text_gray {
  color: rgb(165, 172, 178);
}

.user-table{
  width: 22% !important;
  gap: 10% !important;
}

.name {
  font-weight: bold;
  font-size: 16px;
  line-height: 20px;
}

.phone {
  font-size: 12px;
  color: rgb(140, 145, 150);
  line-height: 18px;
}

.email {
  font-size: 12px;
  color: rgb(140, 145, 150);
  line-height: 18px;
  width: 200px;
}

.tiny {
  border-radius: 2px;
  padding: 2px;
  background-color: rgb(227, 222, 248);
  color: rgb(106, 37, 255);
}
</style>
