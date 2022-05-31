<template>
  <div id="changemain">
    <h1>UPDATE YOUR CREDENTIAL</h1>
    <v-form ref="form" v-model="valid" lazy-validation>
      <v-text-field
        placeholder="Enter your name"
        v-model="posts.name"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your Father's Name"
        v-model="posts.father"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your Mother's Name"
        v-model="posts.mother"
      ></v-text-field>
      <v-text-field
        placeholder="Enter your phone"
        v-model="posts.phone"
      ></v-text-field>
      <v-text-field type="email"
        placeholder="Enter your email"
        v-model="posts.email"
      ></v-text-field>
       <!-- Gender -->
       <v-radio-group v-model="posts.gender" mandatory>
        <v-radio label="Male" value="Male"></v-radio>
        <v-radio label="Female" value="Female"></v-radio>
      </v-radio-group>
       <!-- Date of Birth -->
      <v-text-field type="date" v-model="posts.date"></v-text-field>
       <v-text-field
        placeholder="Enter your district"
        v-model="posts.district"
      ></v-text-field>
       <v-text-field
        placeholder="Enter your pin"
        v-model="posts.pin"
      ></v-text-field>
       <v-text-field
        placeholder="Enter your state"
        v-model="posts.state"
      ></v-text-field>
      <router-link to="/success" id="lc"
        ><v-btn type="submit" id="ubtn" @click="change" dark> Update </v-btn></router-link
      >
    </v-form>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "ChangeForm",
  data() {
    return {
      key: this.$route.params.id,
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
    async change() {
      await axios.put(`http://localhost:3000/employee/${this.key}`, this.posts);
      location.reload()
    },
  },
};
</script>
<style scoped>
#changemain{
  width:50%;
  margin:0 auto;
}
#changemain h1{
  color:red;
  text-align:center
}
#ubtn{
  width:500px;
  font-size:30px;
  margin-left:20px;
}
#lc{
  text-decoration:none;
}
</style>
