<template>
    <div class="login-container">
        <h3>CONNEXION</h3>
    </div>
    <from @submit.prevent="submit">
        <div  class="from-group">
  <input type="email" placeholder=" EMAIL" required v-model="email">
  </div>
  <div class="from-group">
    <input type="password" placeholder="MOT DE PASSE" required v-model="password">
  </div>

<div class="d-grid">
  <input type="submit" v-on:click="submit" > 

</div>
<p> vous n'avez pas encore de compte?</p><a href="#/registerComponent"> s'inscrire</a>

  </from>
  
  </template>
  <script>
  
  export default{
    data(){
        return{
            email:'',
            password:'',
            
              connexion: [
                {email:'',password:''}
              ]
            
        };
    },
    methods:{
        submit(){
          
            const user={
              email:this.email,
              password:this.password
  
            }
            this.connexion.push(user)
            this.email=null
            this.password=null
        }
    }
  }
  
  </script>
  <style>
  .login.container{
    max-width: 400px;
    margin:0 auto;
    padding:20px;
    border:1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
  
  }
 
  
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  body{
    margin:0;
    background: #eee;;
  }
  form{
    max-width: 420px;
    margin: 30px auto;
    background:  white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  
  }
  label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
  
  }
 
  .header{
      text-align: center;
      font-family: sans-serif;
  }
  input{
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  
  }
  .form-group{
      display: flex;
      gap: 2px;
      flex-direction: column;
      width: 95%;
  }
  .form-group button{
      width: 25%;
      padding: 8px 0;
      border: none;
      font-size: large;
      
  }
  .form-group input{
      width: 100%;
      border: 1px solid slategray;
      padding: 7px 2px;
   
    }
      form {
      display: flex;
      flex-direction: column;
      width: 425px;
      padding: 20px;
      margin: 40px;
      border: 2px solid #d8d8d8;
      background-color: white;
      -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
      -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
      box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
    }
    
    .container {
      width: 425px;
      padding: 20px;
      background-color: white;
      -webkit-box-shadow: 0px 2px 20px -12px rgba(0, 0, 0, 0.57);
      -moz-box-shadow: 0px 2px 20px -12px rgba(0, 0, 0, 0.57);
      box-shadow: 2px 20px -12px rgba(0, 0, 0, 0.57);
      margin-left: 40px;
      border: 2px solid #d8d8d8;
    }
    
    .review-container li {
      margin-bottom: 30px;
    }
    
    .review-form .button {
      display: block;
      margin: 30px auto;
    }
    
    @media only screen and (max-width: 600px) {
      .container {
        flex-direction: column;
      }
    
      .product-image,
      .product-info {
        margin-left: 10px;
        width: 100%;
      }
    
      .review-form {
        width: 90%;
      }
    }
  </style>