<template>
  <div class="bg">
    <div class="container">
      <div class="box" v-for="(element, index) in info" :key="index">
        <Brani :box="element" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Brani from "@/components/Brani.vue";
export default {
  name: "Main",
  components: {
    Brani,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      info: [],
    };
  },
  created() {
    this.getArray();
  },
  methods: {
    getArray() {
      axios
        .get(this.apiURL)
        .then((res) => {
          this.info = res.data.response;
          console.log(this.info);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style scoped lang="scss">
.bg {
  width: 100%;
  background-color: #1d2d3c;
}
.container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  max-width: 1200px;
  margin: auto;
  text-align: center;
}

.box {
  width: calc(100% / 8 - 40px);
  margin: 20px;
  padding: 10px;
  background-color: #2e3a46;
}
</style>
