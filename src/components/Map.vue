<template>
  <div class="hello">
    <div id="map">
      <Menu class="menu"></Menu>
    </div>
  </div>
</template>
<script>
import mapboxgl from 'mapbox-gl'
import Menu from './Menu.vue'

export default {
  name: "map",
  props: {
    msg: String,
  },
  data() {
    return {
      message: "你看什么呢",
    };
  },
  methods: {
    // 初始化
    init() {
      mapboxgl.accessToken ="pk.eyJ1IjoiZGFubmVpd3UiLCJhIjoiY2tjb2l5Zjd2MGxlbjJ5bGJmb2YyZGVhcCJ9.Q3KjUgBjdpmudMSWlwIlLQ";
      const map = new mapboxgl.Map({
        container: document.getElementById("map"),
        style: "mapbox://styles/danneiwu/ckcoklae20b7f1ipf92prkexf",
        center: [103.9652064864411, 30.516717608535195], // 设置地图中心
        zoom: 8, // 设置地图比例
      });
      // 点击获取经纬度模块&点击标记点
      map.on('click', function (e) {
            console.log([e.lngLat.lng,e.lngLat.lat])
        })
    },
  },
  mounted() {
    this.init();
  },
   components: {
    Menu
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://api.tiles.mapbox.com/mapbox-gl-js/v0.44.2/mapbox-gl.css");
#map {
  position: relative;
  width: 100%;
  height: 800px;
}
.mapboxgl-ctrl-attrib-inner, .mapboxgl-ctrl{
  display: none;
}
.menu{
  position: absolute;
  left: 1%;
  top: 5%;
}
</style>
