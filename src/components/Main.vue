<template>
  <div class="bg">
    <div class="container">
      <div v-for="(brano, index) in generi" :key="index">
        <Select :select="generi" @filtra="filterGenere" />
      </div>
    </div>
    <div class="container">
      <Brani :box="filtered" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Brani from "@/components/Brani.vue";
import Select from "@/components/Select.vue";

export default {
  name: "Main",
  components: {
    Brani,
    Select,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      info: [],
      generi: {
        genere: [],
      },
      val: "",
    };
  },
  created() {
    this.getArray();
    this.getGenere();
    this.val = "all";
  },
  computed: {
    filtered() {
      if (this.val === "all") {
        return this.info;
      }
      return this.info.filter((element) => {
        return element.genre === this.val;
      });
    },
  },
  methods: {
    getArray() {
      axios
        .get(this.apiURL)
        .then((res) => {
          this.info = res.data.response;
        })
        .catch((err) => {
          console.log(err);
        });
    },
    getGenere() {
      axios.get(this.apiURL).then((res) => {
        res.data.response.forEach((element) => {
          if (!this.generi.genere.includes(element.genre))
            this.generi.genere.push(element.genre);
        });
      });
    },
    filterGenere(valore) {
      this.val = valore;
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
</style>
