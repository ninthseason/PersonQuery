<template>
  <ul>
    <SCard v-for="item in student" :key="item['Id']" :student="item"></SCard>
  </ul>
</template>

<script>
import SCard from "@/components/SCard";
export default {
  name: "SList",
  components: {
    SCard
  },
  props: ["student"]
}
</script>

<style scoped>
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-left: 0;
  }
</style>
