<template>
  <div id="app">
    <vue-pannellum :src="tour" style="height: 500px"></vue-pannellum>
  </div>
</template>

<script>
import VuePannellum from "vue-pannellum";

export default {
  name: "App",
  components: {
    VuePannellum
  },
  data() {
    return {
      tour: {
        default: {
          firstScene: "sea",
          hotSpotDebug: true // для  поиска координат точек на изображении
        },
        scenes: {
          sea: {
            title: "Mason Circle",
            hfov: 110,
            pitch: -3,
            yaw: 117,
            type: "equirectangular",
            panorama:
              "https://mir-s3-cdn-cf.behance.net/project_modules/fs/83832185109119.5e57149f02878.jpg",
            hotSpots: [
              {
                pitch: -1.4,
                yaw: 150,
                type: "scene",
                text: "Spring House or Dairy",
                sceneId: "venezia"
              }
            ]
          },
          venezia: {
            hfov: 110,
            yaw: 5,
            type: "equirectangular",
            panorama:
              "https://roadtovrlive-5ea0.kxcdn.com/wp-content/uploads/2014/09/Venice.Still001.jpeg",
            hotSpots: [
              {
                pitch: -3,
                yaw: -52,
                type: "scene",
                text: "Mason Circle",
                sceneId: "sea"
              }
            ]
          }
        }
      }
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
