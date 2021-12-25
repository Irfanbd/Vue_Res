<template>
  <img class="logo" src="../assets/logo.jpg" alt="" />
  <h1>SignUp</h1>
  <div class="container">
    <div class="register">
      <input type="text" v-model="name" placeholder="Enter Your Name" />
      <input type="text" v-model="email" placeholder="Enter Your Email" />
      <input
        type="password"
        v-model="password"
        placeholder="Enter Your Password"
      />
      <button v-on:click="signup" class="button">Sign Up</button>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "SignUp",
  data() {
    return {
      name: "",
      email: "",
      password: "",
    };
  },
  methods: {
    async signup() {
      let result = await axios.post("http://localhost:3000/users", {
        email: this.email,
        password: this.password,
        name: this.name,
      });
      console.warn(result);
      if (result.status == 201) {
        localStorage.setItem("user-info", JSON.stringify(result.data));
        this.$router.push({ name: "Home" });
      }
    },
  },
};
</script>

<style>
.logo {
  width: 200px;
}
.register input {
  font-family: "Trebuchet MS";
  width: 300px;
  display: block;
  height: 20px;
  padding-left: 15px;
  margin-bottom: 30px;
  margin-right: auto;
  margin-left: auto;
  border: 3px solid orange;
}
.button {
  border: 3px solid skyblue;
  width: 320px;
  height: 40px;
  background: skyblue;
  color: white;
  cursor: pointer;
}
</style>
