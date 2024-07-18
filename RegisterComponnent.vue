<template>
    <form @submit.prevent="submit">
<h1> INSCRIPTION</h1>

  
   <div class="from-group">
   <label for="name">Name</label>
    <input
      id="name"
      v-model="name"
      type="text"
      name="name"></div>
    

    <div class="from-group">
      <label for="prenom">Prenom</label>
    <input
      id="prenom"
      v-model="prenom"
      type="text"
      name="prenom"></div>
    
  
    <div class="from-group">
      <label for="email">email</label>
    <input
      id="email"
      v-model="email"
      type="email"
      name="email"/></div>
    
  
    <div class="from-group"><label for="number">telephone</label>
    <input
      id="number"
      v-model="telephone"
      type="number"
      name="telephone"></div>
    
  
  
    <div class="from-group">
    <label for="password">mot de passe</label>
    <input
      id="password"
      v-model="password"
      type="password"
      name="mot de passe">
    </div>
  

  <div class="from-group">
    <label for="date">date d'enregistrement </label>
 </div>
    
  
  <div>
    <input
      type="submit" value="Submit" >
  </div>
  <p>vous avez déjà un de compte?</p><a href="#/loginComponent">se connecter</a>

  </form>
</template>

<script>
export default({
  data() {
    return{
      name :null,
      prenom :null,
      email : null,
      telephone :null,
      password :null,
      date: null,
      inscription:[
        {name:'',prenom:'',email:'',telephone:'',password:'',date:''}
      ]

    }
  },
  methods: {
    submit() {
      const user= {
        name: this.name,
        prenom:this.prenom,
        email:this.email,
        telephone:this.telephone,
        password:this.password,
        date:this.date
      }
      this.inscription.push(user)
      this.name=null
      this.prenom=null
      this.email=null
      this.telephone=null
      this.password=null
      this.date=null
    }
  },

})



</script>


<style>
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
    padding: 7px 2px;}
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