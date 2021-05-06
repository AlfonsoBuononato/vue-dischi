<template>
  <div class="box-2">
    <img :src="box.poster" alt="" />
    <h3>{{ box.title }}</h3>
    <h4>{{ box.author }}</h4>
    <h5>{{ box.year }}</h5>
    <h6>{{ box.genre }}</h6>
  </div>
</template>

<script>
export default {
  name: "Brani",
  props: ["box"],
};
</script>

<style scoped lang="scss">
.box-2 {
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
