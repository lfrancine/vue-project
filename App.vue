  <template>
  <div>
    <button @click="login">Login Using Google</button>
    <div v-if="userDetails">
      <h2>User Details</h2>
      <p>Email: {{ userDetails.email }}</p>
      <p>Password: {{ userDetails.password }}</p>
      <p>Profile Picture: <img :src="userDetails.picture" alt="Profile Picture"></p>
    </div>
  </div>
  <div>
  <a href ="#/">HomeComponent</a>

<a href ="#/registerComponent">RegisterComponent</a>

<a href ="#/loginComponent">LoginComponent</a>
<component :is="currentView"/></div>
</template>

<script>

import { googleSdkLoaded } from "vue3-google-login";
import axios from "axios";
import LoginComponent from "./components/LoginComponent.vue";
import RegisterComponent from "./components/RegisterComponnent.vue";
import HomeComponent from "./components/HomeComponent.vue";


export default {
components:{
  LoginComponent,
  RegisterComponent,
  HomeComponent
},

data(){
    return {
      userDetails: null,
    };
  
  },
  methods: {
    login() {
      googleSdkLoaded(google => {
        google.accounts.oauth2
          .initCodeClient({
            client_id:
              "58730156701-di0.apps.googleusercontent.com",
            scope: "email profile openid",
            redirect_uri: "http://localhost:4000/auth/callback",
            callback: response => {
              if (response.code) {
                this.sendCodeToBackend(response.code);
              }
            }
          })
          .requestCode();
      });
    },
    async sendCodeToBackend(code) {
      try {
        const headers = {
          Authorization: code
        };
        const response = await axios.post("http://localhost:4000/auth", null, { headers });
        const userDetails = response.data;
        console.log("User Details:", userDetails);
        this.userDetails = userDetails;

        // Redirect to the homepage ("/")
        //this.$router.push("/rex");
      } catch (error) {
        console.error("Failed to send authorization code:", error);
      }
    }
  }
};
</script>