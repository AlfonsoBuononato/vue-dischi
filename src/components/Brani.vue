<template>
  <div class="box">
    <div class="box-2" v-for="(element, index) in box" :key="index">
      <img :src="element.poster" alt="" />
      <h3>{{ element.title }}</h3>
      <h4>{{ element.author }}</h4>
      <h5>{{ element.year }}</h5>
      <h6>{{ element.genre }}</h6>
    </div>
  </div>
</template>

<script>
export default {
  name: "Brani",
  props: ["box"],
};
</script>

<style scoped lang="scss">
.box {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.box-2 {
  width: calc(100% / 8 - 40px);
  margin: 20px;
  background-color: #2a3a46;
  padding: 10px;
  img {
    width: 100%;
  }
  h3 {
    font-size: 15px;
    color: #fff;
    margin-top: 10px;
    margin-bottom: 5px;
  }
  h4,
  h5 {
    color: #565b5d;
  }
  h6 {
    margin-top: 5px;
    color: #fff;
  }
}
</style>
