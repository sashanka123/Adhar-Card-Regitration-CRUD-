<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      :collapse="!collapseOnScroll"
      :collapse-on-scroll="collapseOnScroll"
      absolute
      color="#424242"
      scroll-target="#scrolling-techniques-6"
    >
      <v-toolbar-title><h2>Aadhar Card Registration</h2></v-toolbar-title>
      <v-spacer></v-spacer>
      <router-link to="/createemp" id="link"><v-btn light id="create">Create Registration</v-btn></router-link>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-6"
      class="overflow-y-auto"
      max-height="600"
    >
      <v-container style="height: 60px"></v-container>
    </v-sheet>
  </v-card>
</template>
<script>
export default {
  name: "NavBar",
  data: () => ({
    collapseOnScroll: true,
  }),
};
</script>
<style scoped>
#create{
  box-shadow: 0px 0px 10px white;
  font-weight:700;
}
#link{
  text-decoration:none;
}
h2{
  color:red;
}
</style>
