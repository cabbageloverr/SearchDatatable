<template>
  <div class="box_user card-style">
    <slot>
      <!-- <p class="name">{{ user.name }}</p>
      <p class="phone">
        Phone: {{ user.phones[0] }}
        <span class="border tiny" v-if="user.phones.length > 1">
          +{{ user.phones.length - 1 }}</span
        >
      </p>
      <p class="email">Email: {{ user.email }}</p> -->
    </slot>
  </div>
</template>
<script>
export default {};
</script>
<style lang="css" scoped>
.box_user {
  box-shadow: 0 1px 5px rgb(0 0 0 / 0.2);
  border-radius: 10px;
  align-items: flex-start;
  padding: 12px;
}
</style>
