<template>
  <div class="search-box">
    <div class="field">{{ field_show }}</div>
    <input type="text" placeholder="支持模糊查询" v-model="text">
  </div>
</template>

<script>

export default {
  name: "SearchBox",
  data() {
    return {
      text:"",
    }
  },
  props:["field_show", "field"],
  mounted() {
    this.$bus.$on("onSearch", ()=>{
      let data = {}
      data[this.field] = this.text
      this.$bus.$emit("ReceiveData", data)
    })
  }
}
</script>

<style scoped>
  .field {
    margin-right: 10px;
    display: flex;
    align-items: center;
  }

  .search-box {
    display: inline-flex;
    margin-left: 7px;
    margin-right: 7px;
  }

  .search-box input {
    width: 204px;
    height: 28px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 4px 7px;
  }
  .search-box input:focus {
    outline: none;
    border-color: rgba(82, 168, 236, 0.8);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
  }
</style>
