<script setup>
import {ref} from 'vue'
import axios from 'axios';
import { useRouter } from 'vue-router'


const router = useRouter()

const formData = ref({
  username: '',
  email: '', 
  password: ''  
})

const registerUser = async () => {
  try {
    const response = await axios.post('http://127.0.0.1:8000/api/register', formData.value);
    console.log(response.data) 

    router.push('/login')
  } catch (error) {
    console.error('Error registering user:', error) 
  } 
}

</script>




<template>
 <div class="signup-form container border rounded mt-5">
        <h1 class="text-center mt-5">Signup Here</h1>
      <form @submit.prevent="registerUser">
          <div class="mb-3">
    <label for="username" class="form-label">Username</label>
    <input type="text" class="form-control" value="username"  v-model="formData.username">
  </div>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" value="email"  v-model="formData.email">
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" value="password" v-model="formData.password">
  </div>
  <button type="submit" class="btn btn-secondary mb-5">Submit</button>
</form>
  
    </div>

</template>