<template>
  <div>
    <div v-for="user in state.users" :key="user.id">
        <!-- 1.2 -->
          <!-- RouterLink here -->
        <!-- 1 -->
          <p>FirstName : {{user.first_name}} {{user.last_name}}</p>
          <p>Email: {{user.email}}</p>
          <p>UserID: {{user.id}}</p>
          <img :src="user.avatar" height=100 alt="">
      <div style="border-bottom: 1px solid #88006666; height:2px; margin: 10px 0; width:100%"></div>
      </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'


    const state = ref({
      error: null,
      users: null
    })

    const load = async () => {
      try {
        const usersResponse = await fetch("https://reqres.in/api/users?delay=2")
      
        await usersResponse.json().then(userData => {
          state.value.users = userData.data
        })
      
      }
      
      catch (err) {
        state.value.error = err.message
        console.log(state.value.error)
      }
    }

      await load()
    





</script>

<style lang="scss" scoped>

</style>