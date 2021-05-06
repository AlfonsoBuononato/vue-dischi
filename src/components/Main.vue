<template>
  <div class="bg">
    <div class="container">
      <div class="box" v-for="(element, index) in api.response" :key="index">
        <img :src="element.poster" alt="" />
        <h3>{{ element.title }}</h3>
        <h4>{{ element.author }}</h4>
        <h5>{{ element.year }}</h5>
        <h6>{{ element.genre }}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
      api: {
        success: true,
        response: [
          {
            poster:
              "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg",
            title: "New Jersey",
            author: "Bon Jovi",
            genre: "Rock",
            year: "1988",
          },
          {
            poster:
              "https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg",
            title: "Live at Wembley 86",
            author: "Queen",
            genre: "Pop",
            year: "1992",
          },
          {
            poster:
              "https://images-na.ssl-images-amazon.com/images/I/41JD3CW65HL.jpg",
            title: "Ten's Summoner's Tales",
            author: "Sting",
            genre: "Pop",
            year: "1993",
          },
          {
            poster: "https://cdn2.jazztimes.com/2018/05/SteveGadd-800x723.jpg",
            title: "Steve Gadd Band",
            author: "Steve Gadd Band",
            genre: "Jazz",
            year: "2018",
          },
          {
            poster:
              "https://images-na.ssl-images-amazon.com/images/I/810nSIQOLiL._SY355_.jpg",
            title: "Brave new World",
            author: "Iron Maiden",
            genre: "Metal",
            year: "2000",
          },
          {
            poster:
              "https://upload.wikimedia.org/wikipedia/en/9/97/Eric_Clapton_OMCOMR.jpg",
            title: "One more car, one more raider",
            author: "Eric Clapton",
            genre: "Rock",
            year: "2002",
          },
          {
            poster:
              "https://images-na.ssl-images-amazon.com/images/I/51rggtPgmRL.jpg",
            title: "Made in Japan",
            author: "Deep Purple",
            genre: "Rock",
            year: "1972",
          },
          {
            poster:
              "https://images-na.ssl-images-amazon.com/images/I/81r3FVfNG3L._SY355_.jpg",
            title: "And Justice for All",
            author: "Metallica",
            genre: "Metal",
            year: "1988",
          },
          {
            poster:
              "https://img.discogs.com/KOBsqQwKiNKH-q927oHMyVdDzSo=/fit-in/596x596/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-6406665-1418464475-6120.jpeg.jpg",
            title: "Hard Wired",
            author: "Dave Weckl",
            genre: "Jazz",
            year: "1994",
          },
          {
            poster:
              "https://m.media-amazon.com/images/I/71K9CbNZPsL._SS500_.jpg",
            title: "Bad",
            author: "Michael Jacjson",
            genre: "Pop",
            year: "1987",
          },
        ],
      },
    };
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
  background-color: #2e3a46;
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
