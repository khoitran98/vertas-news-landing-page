<template>
  <div class="home">
    <v-snackbar v-model="snackbar" :timeout="4000" top>
      <span>Awesome! Email submitted</span>
      <v-btn color="white" flat @click="snackbar = false">Close</v-btn>
    </v-snackbar>
    
    <v-container id="box1" class ="mt-100" fill-height fluid>
      <v-layout  class="text-xs-center" align-center>
        <v-flex class=" text white--text">
          Truth Dies In Silence
        </v-flex>
      </v-layout>
    </v-container>
    <v-container id="box2" fill-height fluid>
      <v-layout class="text-xs-center" align-center>
        <v-flex class="text black--text">
          Join Us Before It's Too Late
        </v-flex>
      </v-layout>
    </v-container>
    <v-container id="box3" fill-height fluid>
      <v-layout class="text-xs-center" align-center>
        <v-flex class="black--text">
          <div id="box3-text"> 
            C O M I N G&nbsp;&nbsp; S O O N 
            <br>
            M I D&nbsp;&nbsp; 2 0 1 9 
          </div>
        </v-flex>
      </v-layout>
      <v-footer absolute height="90px" class="white--text" style="background: black;">
        <div>
          <div id="subs" class="text-xs-center">
            <div id="subscribe"> Subscribe to our Newsletter </div>
            <span>
              <v-text-field autofocus flat solo-inverted hide-details
                color="white" id="email" class="white--text" append-outer-icon="send" 
                label= "Email Address" @click:append-outer="submitEmail"
                v-model="email" :rules="emailRules" ref="form"> 
              </v-text-field>
            </span>
          </div>
          <div id="footer-image" class="text-xs-center">
            <div>
              <img src="../assets/final.png" style="width: 115px; height: 43px; border: 1px solid white;">
            </div>
            <div>
              @ Vertas 2019
            </div>
          </div>
          <div  id="act">
            <div> <a class="white--text"> About Us </a> </div>
            <div> <a class="white--text"> Contact </a> </div>
            <div> <a class="white--text"> Terms & Conditions </a> </div>
          </div>
        </div>
      </v-footer>
    </v-container> 
  </div>   
</template>

<script>
import db from '@/fb'

export default {
  name: 'home',
  data() {
    return {
      snackbar: false,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
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
.text{
  font-family: "Times New Roman", Times, serif;
	font-style: italic;
	font-size: 120px;
}
.v-footer {
  height: 90px;
}
#box1 {
	box-shadow: 0px 19.2px 40px rgba(0, 0, 0, .16);
  background: black; 
  margin-top: 163px; 
  height: 300px;
}
#box2 {
	border-top: 1px solid #707070;
  border-bottom: 1px solid #707070;
	box-shadow: 0px 19.2px 40px rgba(0, 0, 0, .08);
  background: white; 
  margin-top: 76px; 
  height: 300px;
}
#box3 {
   position: absolute;
   margin-top: 177px; 
   height: 975px;
}
#box3-text {
   font-family: bebas-neue, sans-serif;
   font-style: normal;
   font-weight: 800;
   font-size: 100px;
}

#email {
  color: white;
} 
#subscribe {
  position: absolute;
  width: 100%;
   left: 0%;
   right: 0%;
   top: 7%;
}
span > .v-text-field {
  border: 1px solid white; 
  width: 15%; 
  left: 42.5%;
  top: 33%;
}
#act {
  position: absolute; 
  left: 3%;
  top: 20%;
}
#footer-image {
  position: absolute;
  right: 3%;
  top: 18%;
}

@media screen and (max-width: 1390px) and (min-width: 1045px){
.text {
	font-size: 90px;
}
#icons {
	width: 12.5%;
	left: 88%
}
span > .v-text-field {
  width: 25%; 
  left: 37.5%;
} 
}

@media screen and (max-width: 1045px) and (min-width: 945px){
#lsa {
	left: 58%;
  width: 35%;
}
#icons {
  display: none;
}
.text {
	font-size: 80px;
}
#box3-text {
  font-size: 90px;
}  
span > .v-text-field {
  width: 25%; 
  left: 37.5%;
} 
}

@media screen and (max-width: 945px) and (min-width: 781px){
#lsa {
	width: 33%;
  left: 60%;
}
#icons {
  display: none;
}
.text {
	font-size: 70px;
}
#box2 {
  height: 280px;
  margin-top: 89px;
}
#box1 {
  height: 280px;
  margin-top: 173px;
}
#box3-text {
  font-size: 75px;
}  
span > .v-text-field { 
  width: 30%; 
  left: 35%;
}
.v-text-field {
  width: 35%;
  left: 23%;
}
}


@media screen and (max-width: 814px){
.text {
	font-size: 45px;
}
#box2 {
  height: 260px;
  margin-top: 89px;
}
#box1 {
  height: 260px;
  margin-top: 173px;
}

#box3-text {
  font-size: 50px;
  position: relative;
  bottom: 80px;
}
#box3 {
  height: 700px;
}
span > .v-text-field {
  width: 25%; 
  left: 37.5%;
}
}

@media screen and (max-width: 600px) {
span > .v-text-field {
  width: 30%; 
  left: 35%;
}
#box3-text {
  font-size: 50px;
  position: relative;
  bottom: 100px;
}
#box3 {
  height: 600px;
}
}

@media screen and (max-width: 540px) {
#box3-text {
  font-size: 40px;
}
}

@media screen and (max-width: 480px) {
.v-footer {
  height: 200px !important;
}
span >.v-text-field {
  top: 20%;
  width: 94%;
  left: 3%;
  height: 50px;
} 
#act {
  top: 60%;
}
#footer-image {
  top: 60%;
}
#box3-text {
  font-size: 35px;
  position: relative;
  bottom: 160px;
}
#box3 {
  height: 600px;
}
}

@media screen and (max-width: 380px) {
#box3-text {
  font-size: 32px;
  position: relative;
  bottom: 160px;
}
#box3 {
  height: 600px;
}
}

@media screen and (max-width: 320px) {
#box3-text {
  font-size: 28px;
  position: relative;
  bottom: 160px;
}
#box3 {
  height: 600px;
}
}

</style>




