<template>
  <v-container>
      <v-row>
          <v-col cols="5">
              <v-img src="https://t3.ftcdn.net/jpg/02/35/74/60/360_F_235746046_IvDBbrZSTttLTOK0VCW0PKarSvpodhSm.jpg"></v-img>
          </v-col>
      </v-row>
      <v-row>
          <v-col cols="5">
              <h3>YOU HAVE BEEN SUCCESSFULLY DONE</h3>
          </v-col>
          <v-col cols="5">
             <router-link to="/" id="home"><v-btn id="btn">GO TO HOME</v-btn></router-link> 
          </v-col>
      </v-row>
  </v-container>
</template>

<script>
export default {

}
</script>

<style>
#home{
    text-decoration:none;
}
#btn{
    width:200px;
    height:50px;
    background-color: #424242;
    color:white;
}
</style>