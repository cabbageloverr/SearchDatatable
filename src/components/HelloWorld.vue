<template>
  <div class="search-container ">
    <form action="">
      <input type="text" placeholder="Search..." name="search">
      <button type="submit">search</button>
      <b-button variant="danger">Button</b-button>
    </form>
    <table class="table">
    <thead class="thead">
    <tr>
      <th scope="col"></th>
      <th scope="col">Fullname</th>
      <th scope="col">Phones</th>
      <th scope="col">Email</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="user in users" :key="user.id" class="user">
      <th scope="row"></th>
      <td >
        <a>{{ user.name }}</a>
      </td>
      <td> {{ user.phones.join() }}</td>
      <td> {{ user.email }}</td>
    </tr>
    
  </tbody>
</table>
</div>
  
</template>

<script>
export default {
    data() {
      return {
        
        users: []
      }
    },
    mounted() {
      fetch('http://localhost:3000/users')
        .then((res) => res.json())
        .then( data => this.users = data)
        .catch( err => console.log(err.message))
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
