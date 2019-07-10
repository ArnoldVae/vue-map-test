<template>
  <div >

    <baidu-map class="bm-view" :scroll-wheel-zoom="true" center="北京" :zoom="4">
      <bm-marker @dblclick="clickHandler" :position="op"  @click="infoWindowOpen" v-for="(op,index) in points" :title="op.lng">
      </bm-marker>
<!--      <bm-point-collection :points="points" shape="BMAP_POINT_SHAPE_STAR" color="red" size="BMAP_POINT_SIZE_SMALL" @click="clickHandler"></bm-point-collection>-->
    </baidu-map>
  </div>
</template>WW

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    show:true,
    points: []
  },
  mounted(){
    const points = [];
    for (var i = 0; i < 100; i++) {
      const position = {lng: Math.random() * 40 + 85, lat: Math.random() * 30 + 21}
      points.push(position)
    }
    this.points = points
  },
  methods: {
    clickHandler (e) {
      alert('aaaaaaaaaaaaa');
    },
    addPoints () {
      const points = [];
      for (var i = 0; i < 100; i++) {
        const position = {lng: Math.random() * 40 + 85, lat: Math.random() * 30 + 21}
        points.push(position)
      }
      this.points = points
    },
    infoWindowClose () {
      this.show = false
    },
    infoWindowOpen () {
      this.show = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.bm-view {
  width: 100%;
  height:400px;
}
</style>
