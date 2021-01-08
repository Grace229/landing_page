<template>
  <div>
    <v-row class="centerD" no-gutters>
      
      <p class="text">{{ data.name }}</p>
    </v-row>
    <div class="icons">
    <ul>
      <li> <i class="fab fa-instagram"></i></li>
      <li> <i class="fab fa-twitter-square"></i></li>
      <li>  <i class="fab fa-snapchat-square"></i></li>
      <li>  <i class="fas fa-envelope-square"></i></li>
    </ul>
  </div>
    <imageCard />
    <menuFooter />
  </div>
</template>

<script>
import api from "../../services/api";
import imageCard from "@/components/imageCard";
import menuFooter from "@/components/menuFooter";

export default {
  name: "Home",
  mixins: [api],
  data() {
    return {
      data: [],
    };
  },
  async mounted() {
    const userData = {
      name: "AQUILA AVEION",
      social_media: {
        twitter: "aquilaveion",
        instagram: "aquilaveionofficial",
        snapchat: "aquilaveionsnaps",
        email: "aquilaveion@aquil.com",
      },
    };
    const { data } = await this.getUserData(userData);
    this.data = data;
    console.log(data);
  },
  components: { imageCard, menuFooter },
};
</script>

<style scoped>
.text {
  color: white;
  font-family: "Poiret One", cursive;
  font-size: 1em;
  letter-spacing: 9px;
}

.centerD {
  position: relative;
  top: 2vh;
  width: 40%;
  left: 10.5vw;
  margin: auto;
}
</style>
