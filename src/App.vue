<template>
  <div id="app">
    <div class="np-credits">wwww.nightprogrammer.com</div>
    <div>
      <img
        :src="$options.imageSource"
        :class="{
          'img-default-size': true,
          'img-enlarged-size': imageEnlarged,
        }"
        @mouseover="enlargeImage"
        @mouseout="shrinkImage"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  created() {
    this.$options.imageSource =
      "https://images.unsplash.com/photo-1564507592333-c60657eea523";
  },
  data() {
    return {
      imageEnlarged: false,
    };
  },
  methods: {
    enlargeImage() {
      console.log("enlarged");
      this.imageEnlarged = true;
    },
    shrinkImage() {
      this.imageEnlarged = false;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}
.img-default-size {
  height: 200px;
  transition: all 0.2s;
}

.img-enlarged-size {
  height: 400px;
  transition: all 0.2s;
}

.np-credits {
  font-size: 12px;
  margin-bottom: 12px;
  color: #4b4b4b;
}
</style>