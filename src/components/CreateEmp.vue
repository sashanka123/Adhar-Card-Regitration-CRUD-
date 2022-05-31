<template>
  <div id="maind">
    <h1>FILL YOUR YOUR CREDENTIAL</h1>
    <v-form>
      <v-text-field
        placeholder="Enter your name"
        v-model="posts.name"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your Father's Name"
        v-model="posts.father"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your mother's name"
        v-model="posts.mother"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your phone number"
        v-model="posts.phone"
      ></v-text-field>
      <v-text-field
      type="email"
        placeholder="Enter your email"
        v-model="posts.email"
      ></v-text-field>
      <!-- Radio Button -->
      <v-radio-group v-model="posts.gender" mandatory>
        <v-radio label="Male" value="Male"></v-radio>
        <v-radio label="Female" value="Female"></v-radio>
      </v-radio-group>
      <!-- Date of Birth -->
      <v-text-field type="date" v-model="posts.date"></v-text-field>
      <v-text-field
        placeholder="Enter your District"
        v-model="posts.district"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your Pincode"
        v-model="posts.pin"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your State"
        v-model="posts.state"
      ></v-text-field>
      <router-link to="/success"
        ><v-btn type="submit" @click="postData" dark>
          Submit
        </v-btn></router-link
      >
    </v-form>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "CreateEmp",
  data(){
    return {
      items:['Bengaluru','Delhi','Mumbai','Chennai'],
      posts: {
        name: "",
        father: "",
        mother: "",
        phone: "",
        email: "",
        date: "",
        gender: "",
        district: "",
        pin: "",
        state: "",
      },
  };
  },
  methods: {
    postData() {
      axios.post("http://localhost:3000/employee", this.posts).then(res => {
        console.log(res);
        location.reload();
      });
    },
  },
};
</script>
<style scoped>
#maind {
  width: 50%;
  margin: 0 auto;
}
#maind h1{
  color:red;
text-align:center;
}
</style>
