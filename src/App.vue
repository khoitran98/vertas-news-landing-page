 <template>
  <div id="app">
    <v-app style="background: white;">

      <v-snackbar v-model="snackbar" :timeout="4000" top>
        <span>Awesome! Email submitted</span>
        <v-btn color="white" flat @click="snackbar = false">Close</v-btn>
      </v-snackbar>

      <v-toolbar color="#EEEEEE" height="90px" style="border-bottom: 1px solid #707070;" flat fixed>
        <img id="title-image" src="../src/assets/final_logo.jpg" aspect-ratio = "1.11">
        <v-text-field id="search" flat solo-inverted hide-details color="black" append-icon="search" background-color="white"> </v-text-field>
        <div id="lsa">
          <v-btn color="#707070" class="toolbar-link" flat> Learn </v-btn>
          <v-btn color="#707070" class="toolbar-link" flat> Support </v-btn>
          <v-btn color="#707070" class="toolbar-link" flat> About </v-btn>
        </div>  
        <div id="icons">
          <v-btn icon class="icon">
            <v-icon color ="#707070"> fab fa-twitter </v-icon>
          </v-btn>
          <v-btn icon class="icon">
            <v-icon color ="#707070"> fab fa-facebook-f </v-icon>
          </v-btn>
          <v-btn icon class="icon">
            <v-icon color="#707070"> fas fa-bell </v-icon>
          </v-btn>
          <v-btn icon class="icon">
            <v-icon color="#707070"> fa fa-user </v-icon>
          </v-btn>
        </div> 
      </v-toolbar>

      <router-view> </router-view>

      <v-footer app class="white--text" height="90px" style="background: black;">
        <div class="text-xs-left" style="position: absolute; left: 3%;">
          <div> <a class="white--text"> About Us </a> </div>
          <div> <a class="white--text"> Contact </a> </div>
          <div> <a class="white--text"> Terms & Conditions </a> </div>
        </div>
        <div class="text-xs-center">
          <div id="subscribe"> Subscribe to our Newsletter </div>
          <span>
            <v-text-field autofocus flat solo-inverted hide-details
              color="white" id="email" class="white--text" append-outer-icon="send" 
              label= "Email Address" @click:append-outer="submitEmail"
              v-model="email" :rules="emailRules" ref="form" lazy-validation> 
            </v-text-field>
          </span>
        </div>
        <div class="text-xs-center" style="position: absolute; right: 3%;">
          <div>
           <img id="logo" src="../src/assets/final.png" style="width: 115px; height: 43px; border: 1px solid white;">
          </div>
          <div>
            @ Vertas 2019
          </div>
        </div>
      </v-footer>

    </v-app>
  </div>
</template>

<script>
import db from '@/fb'

export default {
  name: 'App',
  data() {
    return {
      snackbar: false,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
        v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ]
    };
  },
  methods: {
    submitEmail() {
      if(this.$refs.form.validate()) {
        const email = {
          email_address: this.email
        }
        db.collection('emails').add(email).then(() => {
            this.snackbar = true
          })
      }
    }
  }
}
</script>

<style>
#search {
 color: black;
}
.v-btn--active, .v-btn:hover, .v-btn:focus {
    background-color: white;
}
#title-image {
	position: absolute;
	top: 0;
	left: 5.5%;
  max-height: 110px;
}
.v-text-field {
	width: 25%;
	position: absolute;
	right: 52%;
}
#icons {
	position: absolute;
	display: flex;
	width: 12.5%;
	left: 90%
}
#lsa {
	position: absolute;
	display: flex;
	
	left: 55%;
	width: 30%;
}
.toolbar-link {
   font-family: bebas-neue, sans-serif;
   font-style: normal;
   font-weight: 800;
   width: 33.33%;
   font-size: 16px;
}
.icon {
	width: 12%;
  margin: 0px 0px 0px 0px;
  
}
#email {
  color: white;
}
#subscribe {
  position: absolute;
   left: 40%; 
   right: 40%; 
   width: 20%; 
   top: 7%;
}
span > .v-text-field {
  border: 1px solid white; 
  width: 15%; 
  left: 42.5%;
  top: 33%;
}
@media screen and (max-width: 1290px) and (min-width: 960px) {
#icons {
  display: none;
}
#lsa {
  width: 36%;
}
span > .v-text-field {
  width: 25%; 
  left: 37.5%;
}
}
@media screen and (max-width: 960px) and (min-width: 600px) {
  #icons {
  display: none;
}
.v-text-field {
  left: 200px;
  width: 60%;
}
#lsa {
  display: none;
}
#subscribe {
  width: 40%;
  left: 30%;
}
span > .v-text-field { 
  width: 30%; 
  left: 35%;
}
}
@media screen and (max-width: 600px) {
  #icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
	left: 4%;
}
.v-text-field {
  left: 150px;
  width: 60%;
}
#subscribe {
  width: 50%;
  left: 25%;
}
#lsa {
  display: none;
}
#logo {
  height: auto; 
  width: auto; 
  max-width: 80px; 
  max-height: 30px;
}
span > .v-text-field {
  width: 30%; 
  left: 35%;
}
}
</style>
