<template>
  <CardStyle class="card-user">
    <p class="name">{{ user.name }}</p>
    <p class="phone">
      Phone: {{ user.phones[0] }}
      <span class="border tiny" v-if="user.phones.length > 1">
        +{{ user.phones.length - 1 }}</span
      >
    </p>
    <p class="email">Email: {{ user.email }}</p>
  </CardStyle>
</template>
<script>
import CardStyle from "./CardStyle.vue";
export default {
  props: ["user"],
  components: {
    CardStyle,
  },
};
</script>
<style lang="css" scoped></style>
