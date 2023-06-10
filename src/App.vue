<template>
  <div id="app">
    <!-- <HelloWorld/> -->
    <UsersTable :users="users" ></UsersTable>
  </div>
</template>

<script>
import UsersTable from './components/UsersTable.vue';
// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    UsersTable
},
  data: () => ({
    
"users":
[
    {
        "name": "Ira Pena",
        "phones": [
            "0646674014",
            "0120306682"
        ].join(),
        "email": "posuere.enim@aol.net"
    },
    {
        "name": "Angelica Acosta",
        "phones": [
            "0898521756",
            "0145771902",
            "0226683445"
        ].join(),
        "email": "vitae.risus@protonmail.ca"
    },
    {
        "name": "Ryder Fry",
        "phones": [
            "0421176127"
        ].join(),
        "email": "condimentum@hotmail.com"
    },
    {
        "name": "Brenna Cantu",
        "phones": [
            "0789387464"
        ].join(),
        "email": "ante.blandit@outlook.edu"
    },
    {
        "name": "Camille Chen",
        "phones": [
            "0236914815",
            "0066369895"
        ].join(),
        "email": "orci.lacus@google.org"
    },
    {
        "name": "Dorothy Hickman",
        "phones": [
            "0144522166"
        ].join(),
        "email": "urna.nullam.lobortis@protonmail.org"
    },
    {
        "name": "Hamilton Foley",
        "phones": [
            "0803922598",
            "0112140390",
            "0534780149"
        ].join(),
        "email": "egestas@protonmail.edu"
    },
    {
        "name": "Timothy Powers",
        "phones": [
            "0664320066"
        ].join(),
        "email": "posuere.cubilia.curae@google.org"
    },
    {
        "name": "Lani Spence",
        "phones": [
            "0610714706",
            "0957695783"
        ].join(),
        "email": "sit@google.org"
    },
    {
        "name": "Stuart Fowler",
        "phones": [
            "0868503448"
        ].join(),
        "email": "facilisis.magna@icloud.com"
    },
    {
        "name": "Kelsey Henry",
        "phones": [
            "0318278758",
            "0283446951"
        ].join(),
        "email": "ligula.nullam.feugiat@aol.org"
    },
    {
        "name": "Martena Frederick",
        "phones": [
            "0331473682",
            "0982513532"
        ].join(),
        "email": "purus.accumsan@hotmail.edu"
    },
    {
        "name": "Vincent Pena",
        "phones": [
            "0878386128"
        ].join(),
        "email": "in.felis@outlook.edu"
    },
    {
        "name": "Uriah Pace",
        "phones": [
            "0678874348"
        ].join(),
        "email": "nullam@google.ca"
    },
    {
        "name": "Giselle Carson",
        "phones": [
            "0336181381"
        ].join(),
        "email": "aliquam.adipiscing.lacus@yahoo.ca"
    },
    {
        "name": "Quynn Hutchinson",
        "phones": [
            "0712813712"
        ].join(),
        "email": "duis.dignissim.tempor@yahoo.edu"
    },
    {
        "name": "Rhoda Mcfarland",
        "phones": [
            "0618196861"
        ].join(),
        "email": "ornare@google.couk"
    },
    {
        "name": "Rooney Collins",
        "phones": [
            "0588728336"
        ].join(),
        "email": "integer@aol.com"
    },
    {
        "name": "Peter Simmons",
        "phones": [
            "0044712169"
        ].join(),
        "email": "nunc.sed@icloud.com"
    },
    {
        "name": "Karly Bolton",
        "phones": [
            "0472254877"
        ].join(),
        "email": "sem.egestas@aol.net"
    },
    {
        "name": "Brielle Stuart",
        "phones": [
            "0184211866"
        ].join(),
        "email": "luctus.et@icloud.org"
    }
]

  })
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-left: 2rem;
  margin-right: 2rem;
  color: #2c3e50;
  margin-top: 60px;
 
}
</style>
