<template>
  <h2>Vue 3 Multiple select and show preview</h2>
  <div style="position: relative;left: 30%;width: 40%;">
    <vue-multi-image-upload @data-image="images" :max="4" :data-reset="component" :options="options" :image-size="imageSize"
    :image-format="formatType" />
  </div>
 
  <button @click="component.clear = true">Clear</button>
</template>

<script>
import { VueMultiImageUpload } from '@zakerxa/vue-multiple-image-upload';
export default {
  name: 'App',
  components: {
    VueMultiImageUpload
  },
  data() {
    return {
      component: {},
      options: {},
      imageSize: 2000000, // 2MB
      formatType: ['image/jpeg', 'image/png', 'image/jpg']
    }
  },
  methods: {
    images(e) {
      e.map(res => console.log(res))
    },
    clear() {
      this.component.clear = true;
    }
  },
  mounted() {
    this.options.max = "Max";
    this.options.ready = "Ready";
    this.options.select = "Choosed";
  }
}
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
button{
    width: 150px;
    background-color: #41b883;
    height: 40px;
    border: 0px;
    border-radius: 5px;
    color: white;
}
</style>
