<template>
  <div class="home">
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
          <div> 
            C O M I N G&nbsp;&nbsp; S O O N 
            <br>
            M I D&nbsp;&nbsp; 2 0 1 9 
          </div>
        </v-flex>
      </v-layout>
    </v-container> 
  </div>   
</template>

<script>
// @ is an alias to /src
export default {
  name: 'home',
  data() {
    return {
    };
  }
}
</script>

<style>
.text{
  font-family: "Times New Roman", Times, serif;
	font-style: italic;
	font-size: 120px;
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
   font-family: bebas-neue, sans-serif;
   font-style: normal;
   font-weight: 800;
   font-size: 100px;
   position: absolute;
   margin-top: 177px; 
   height: 975px;
}
@media screen and (max-width: 1390px) and (min-width: 1060px){
.text {
	font-size: 90px;
}
}
@media screen and (max-width: 1060px) and (min-width: 945px){
.text {
	font-size: 80px;
}
#box3 {
  font-size: 90px;
}  
}
@media screen and (max-width: 945px) and (min-width: 600px){
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
#box3 {
  font-size: 75px;
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
#box3 {
  font-size: 50px;
}  
}
</style>




