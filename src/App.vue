<script setup>
import { ref } from 'vue'

const username = ref('')
const avatarUrl = ref('')
const error = ref('')
const isLoading = ref(false)

async function searchUser() {
  if (!username.value.trim()) {
    error.value = 'Please enter a username'
    return
  }

  isLoading.value = true
  error.value = ''
  avatarUrl.value = ''

  try {
    const response = await fetch(`https://api.github.com/users/${username.value}`)
    
    if (!response.ok) {
      throw new Error('User not found')
    }

    const data = await response.json()
    avatarUrl.value = data.avatar_url
  } catch (e) {
    error.value = e.message
  } finally {
    isLoading.value = false
  }
}
</script>

<template>
  <main>
    <h1>GitHub User Search</h1>
    <input 
      v-model="username" 
      type="text" 
      placeholder="Type a GitHub username"
      @keyup.enter="searchUser"
    />
    <button @click="searchUser" :disabled="isLoading">
      {{ isLoading ? 'Searching...' : 'Search' }}
    </button>
    <img v-if="avatarUrl" :src="avatarUrl" alt="User avatar" class="avatar" />
    <p v-if="error" class="error">{{ error }}</p>
  </main>
</template>

<style scoped>
main {
  text-align: center;
  padding: 2rem;
}

input {
  padding: 10px;
  font-size: 16px;
  width: 250px;
  margin-top: 1rem;
  margin-right: 8px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

button:disabled {
  cursor: not-allowed;
  opacity: 0.6;
}

.error {
  color: red;
  margin-top: 1rem;
}

.avatar {
  display: block;
  margin: 1rem auto 0;
  width: 200px;
  height: 200px;
  border-radius: 50%;
}
</style>
