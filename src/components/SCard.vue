<template>
  <li>
    <div class="card">
      <div id="name">
        {{ name }}
      </div>
      <div id="info">
        📃 学号: {{ id }}<br/>
        🏠 学院: {{ college }}<br/>
        📕 专业: {{ major }}<br/>
        🐧 社交: {{ QQ }}
      </div>
    </div>
  </li>
</template>

<script>
export default {
  name: "SCard",
  props:["student"],
  computed: {
    id() {
      return this.student["Id"]
    },
    name() {
      return this.student["Name"]
    },
    college() {
      return this.student["College"]
    },
    major() {
      return this.student["Major"]
    },
    QQ() {
      return this.student["QQ"]
    }
  }
}
</script>

<style scoped>
  #name {
    color: mediumpurple;
    font-size: 16px;
    font-weight: bold;
    margin-left: 20px;
    margin-top: 10px;
  }

  #info {
    font-size: 14px;
    font-weight: bold;
    margin-top: 10px;
    margin-left: 20px;
    line-height: 1.6;
  }

  li {
    list-style-type: none;
  }

  .card {
    width: 350px;
    height: 150px;
    border: #cccccc solid 1px;
    border-radius: 5px;
    margin: 2px
  }
</style>
