  
<template>
  <div class="manga">
    <div class="container">
      <div class="row">
        <div class="col col-6">
          <b-card style="width: 15rem;">
            <h3>{{ toonList.title_english }}</h3>
          </b-card>
        </div>
        <div class="col col-12">
          <b-card style="width: 15rem;">
            <img :src="toonList.image_url" fluid alt="Responsive image" />
            <b-card-text style="width: 15rem;">
               <br><h5>{{toonList.synopsis}}</h5>
            </b-card-text>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<template>



</template>

<script>
import axios from 'axios'
export default {
data() {
    return {
      toonList: "",
      url: `https://api.jikan.moe/v3/manga/${this.$route.params.id}`,
    };
  },
  
  mounted() {
    axios
      .get(this.url)
      .then((response) => {
        this.toonList = response.data;
      })
      .catch((err) => {
        console.log(err);
        alert(err);
      });
  },
}
</script>

<style>
</style> 