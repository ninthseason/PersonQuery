<template>
  <div id="app">
    <div id="head">
      <SearchBox field_show="学号" field="id"></SearchBox>
      <SearchBox field_show="姓名" field="name"></SearchBox>
      <SearchBox field_show="学院" field="college"></SearchBox>
      <SearchBox field_show="专业" field="major"></SearchBox>
      <SearchBox field_show="社交" field="QQ"></SearchBox>
      <button class="btn btn-danger" @click="Search">查找</button>
    </div>
    <div>
      <SList :student="student"></SList>
    </div>
  </div>
</template>

<script>

import SearchBox from "@/components/SearchBox";
import SList from "@/components/SList";
import axios from "axios";

export default {
  name: 'App',
  data() {
    return {
      fields:{
        id: "",
        name: "",
        college: "",
        major: "",
        QQ: ""
      },
      student:[]
    }
  },
  components: {
    SearchBox,
    SList
  },
  methods:{
    Search() {
      this.$bus.$emit("onSearch");
      // console.log(this.fields)
      axios.get("http://127.0.0.1:8080/user", {params: {id:this.fields["id"],
          name:this.fields["name"],
          college:this.fields["college"],
          major:this.fields["major"],
          QQ:this.fields["QQ"]}}).then(res=>{
        this.student=res.data}).catch(err=>{
        console.log(err)})
    }
  },
  mounted() {
    this.$bus.$on("ReceiveData", (data)=>{
      this.fields[Object.keys(data)[0]] = Object.values(data)[0]
    });
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

#head {
  display: flex;
  justify-content: center;
}

.btn {
  display: inline-block;
  padding: 4px 64px;
  margin-left: 10px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}
.btn-danger {
  color: #fff;
  background-color: #4992da;
  border: 1px solid #2f50bd;
}
.btn-danger:hover {
  color: #fff;
  background-color: #256498;
}
.btn:focus {
  outline: none;
}
</style>
