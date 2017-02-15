<template>
  <div class="home">
    <h1>Welcome Home</h1>
    <p>Create awesome apps with vuejs &amp; meteor! <a href="https://github.com/Akryum/meteor-vue-component">More info</a></p>
    <img src="/img/vue.png" class="logo"/><img src="/img/meteor.png" class="logo"/>

     <gmap-map
    v-if="!loading"
    :center="center"
    :zoom="18"
    style="width: 100%; height: 300px;"
    >

    </gmap-map>

  </div>
</template>

<style scoped>
.home {
  text-align: center;
}
img.logo {
  max-width: 101px;
  margin: 12px;
}
</style>

<script>

  import VueGoogleMaps from 'vue2-google-maps';


  Vue.use(VueGoogleMaps, {
    load: {
      v: '3',
      key: 'AIzaSyDaFZYxlz2oIvQNrMWJKDCMGjhpDMPfBVY',
      libraries: 'geometry,places'
    }
  });

   export default {
    data() {
      return {
        loading: false,
        center: { lat: 0, lng: 0 },
        content: 'Your current Location',
        markers: [{
          position: {lat: 10.0, lng: 10.0}
        }, {
          position: {lat: 11.0, lng: 11.0}
        }]
      }
    }
  }
</script>