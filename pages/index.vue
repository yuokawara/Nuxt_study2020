<template>
  <div class="container">
    <h1>Axios使用中</h1>
    <router-link></router-link>
    <hr>
    <!-- {{ users[0].id }}, {{ users[0].name }} -->
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.id }}, {{ user.name }}, {{ user.email }}
      </li>
    </ul>
    <hr>
    <img src="~/assets/cat.jpg">
  </div>
</template>

<script>
const axios = require('axios')
let url = 'https://jsonplaceholder.typicode.com/users'

export default {
  asyncData({ params, error }) {
    return axios.get(url)
    .then((res) => {
      return { users: res.data }
    })
    .catch((e => {
      // console.log(e.response.status)
      error({ users: e.response.status, message: e.message })
    }))
  },
}
</script>

<style>
</style>
