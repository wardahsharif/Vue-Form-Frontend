<script setup>
import {ref} from 'vue'
import axios from 'axios';
import { useRouter } from 'vue-router'


const router = useRouter()

const formData = ref({
  email: '',
  password: ''
})

const loginUser = async () => {
  try {
    const response = await axios.post('http://127.0.0.1:8000/api/login', formData.value)
    console.log(response.data)

    router.push('/dashboard')
  } catch (error) {
    console.error('Error logging in:', error)
  }
}

const goToForgotPassword = () => {
  router.push('/forgot-password')
}
</script>



<template>
     <div class="signup-form container border rounded mt-5">
        <h1 class="text-center mt-5">Login</h1>

      <form @submit.prevent="loginUser">
   
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" value="email"  v-model="formData.email">
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" value="password" v-model="formData.password">
  </div>
  <button type="submit" class="btn btn-secondary mb-5">Submit</button>
   <a href="#" @click.prevent="goToForgotPassword" class="forgot-password-link">Forgot Password?</a>
</form>
  
    </div>
</template>