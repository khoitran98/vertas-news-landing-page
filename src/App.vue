 <template>
  <div id="app">
    <v-app style="background: white;">

      <v-toolbar id="tlbar" color="#EEEEEE" height="90px" style="border-bottom: 1px solid #707070;" flat fixed>
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
    </v-app>
  </div> 
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
    };
  },
  methods: { 
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
@media screen and (max-width: 1080px) {
.v-text-field {
  position: absolute;
  width: 35%;
  left: 20%;
}


}
@media screen and (max-width: 780px) {
#icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
	left: 4%;
}
.v-text-field {
  left: 175px;
  width: 75%;
}
#lsa {
  display: none;
}
}
@media screen and (max-width: 680px) {
#icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
	left: 4%;
}

#lsa {
  display: none;
}
}

@media screen and (max-width: 610px) {
#icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
	left: 4%;
}
.v-text-field {
  left: 175px;
  width: 65%;
}
#lsa {
  display: none;
}
}
@media screen and (max-width: 480px) {
.v-text-field {
  left: 155px;
  width: 65%;
}
}

@media screen and (max-width: 414px) {
#icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
	left: 2%;
}
.v-text-field {
  left: 140px;
  width: 65%;
}
#lsa {
  display: none;
}
}

@media screen and (max-width: 380px) {
#icons {
  display: none;
}
#title-image {
	position: absolute;
	top: 0;
  height: 100px;
	left: 2%;
}
.v-text-field {
  left: 135px;
  width: 60%;
}
#lsa {
  display: none;
}
}

@media screen and (max-width: 320px) {
.v-text-field {
  left: 118px;
  width: 60%;
}
#title-image {
	position: absolute;
	top: 0;
  height: 90px;
	left: 2%;
}
}

</style>
