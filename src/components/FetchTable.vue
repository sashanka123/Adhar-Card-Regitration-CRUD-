<template>
  <div>
    <NavBar></NavBar>
    <v-container>
      <v-row>
        <v-col cols="8">
          <v-text-field id="search" solo v-model="sdata"></v-text-field>
        </v-col>
        <v-col><v-btn @click="search" id="searchbtn">Search</v-btn></v-col>
      </v-row>
    </v-container>
    <v-simple-table dark>
      <template v-slot:default>
        <thead>
          <tr>
            <th class="text-left">Name</th>
            <th class="text-left">Father's Name</th>
            <th class="text-left">Mother's Name</th>
            <th class="text-left">Mobile Number</th>
            <th class="text-left">Email</th>
            <th class="text-left">Gender</th>
            <th class="text-left">Date of Birth</th>
            <th class="text-left">District</th>
            <th class="text-left">Pincode</th>
            <th class="text-left">State</th>
            <th class="text-left">Edit</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in list" :key="item.id">
            <td>{{ item.name }}</td>
            <td>{{ item.father }}</td>
            <td>{{ item.mother }}</td>
            <td>{{ item.phone }}</td>
            <td>{{ item.email }}</td>
            <td>{{ item.gender }}</td>
            <td>{{ item.date }}</td>
            <td>{{ item.district }}</td>
            <td>{{ item.pin }}</td>
            <td>{{ item.state }}</td>
            <td>
              <v-btn @click="change(item.id)" id="ebtn" elevation="2"
                >EDIT</v-btn
              >
            </td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>
  </div>
</template>

<script>
import axios from "axios";
import NavBar from "./NavBar.vue";
export default {
  name: "FetchTable",
  components: {
    NavBar,
  },
  data() {
    return {
      list: [],
      sdata:''
    };
  },
  mounted() {
    let fetch = async () => {
      let data = await axios.get("http://localhost:3000/employee");
      console.log(data.data);
      this.list = data.data;
    };
    fetch();
  },
  methods: {
    change(val) {
      this.$router.push(`/change/${val}`);
    },
    search(){
      this.list=this.list.filter(e=>{
        if(this.sdata===e.name){
          return e;
        }
      })
      console.log(this.list);
    }
  },
};
</script>

<style>
#dbtn {
  box-shadow: 0px 0px 6px black;
  background-color: red;
  color: white;
}
#ebtn {
  box-shadow: 0px 0px 6px black;
  background-color: green;
  color: white;
}
#sbtn {
  box-shadow: 0px 0px 6px black;
  background-color: blue;
  color: white;
}
#search{
  background-color: #455A64;
  color:white
}
#searchbtn{
  background-color:#3D5AFE;
  color:white;
  width:200px;
  height:50px;
  box-shadow:7px 7px 6px black;
}

</style>
