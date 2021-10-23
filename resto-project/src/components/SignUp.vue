<template>
<img class="logo" src="../assets/logo.jpg" alt="">
    <h1>SignUp</h1>
    <div class="container">

<div class="register">
<input type="text" placeholder="Enter Your Name"/>
<input type="text" placeholder="Enter Your Email"/>
<input type="password" placeholder="Enter Your Password"/>
<button class="button">Sign Up</button>
</div>


    </div>


</template>
<script>
export default {
    name:'SignUp'
}
</script>

<style>
.logo{
    width: 200px;
}
.register input{
    font-family: 'Trebuchet MS';
    width:300px;
    display: block;
    height: 20px;
    padding-left: 15px;
    margin-bottom:30px;
    margin-right: auto;
    margin-left: auto;
    border: 3px solid orange;
}
.button{
    border: 3px solid skyblue;
    width: 320px;
    height: 40px;
    background: skyblue;
    color: white;
    cursor: pointer;
}

</style>

