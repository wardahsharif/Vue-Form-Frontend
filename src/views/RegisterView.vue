<script scope>


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