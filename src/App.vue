<template>
  <div id="app">
    <h1>Random Gift Cat</h1>
    <section class="red">
      <form >
        <div><label>Title:</label>
          <input type="text" class="form-title" v-model="title">
        </div>
        <div class="form-group">
          <label>Filter:</label>
          <select class="form-control" v-model="filter">
            <option value="blur">Blur</option>
            <option value="pixel">Pixel</option>
            <option value="negative">Negative</option>
            <option value="mono">Mono</option>
            <option value="sepia">Sepia</option>
            <option value="paint">Paint</option>
          </select>
        </div>
        <div>
          <label>Color:</label>
          <select class="form-control" v-model="color">
            <option value="green">Green</option>
            <option value="orange">Orange</option>
            <option value="purple">Purple</option>
            <option value="yellow">Yellow</option>
            <option value="red">Red</option>
            <option value="blue">Blue</option>
          </select>
        </div>
        <div>
          <label>Size:</label>
          <input type="text" class="form-control" v-model="size" @keyup.enter="showImage">
        </div>
      </form>
    </section>
    <button type="button" class="btn btn-success" @click="showImage">I want my gatito!!</button>
    <section id="image">
      <div class="">
        <img :src="ImageUrl" alt="">
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'Random Gif Cat',
      ImageUrl: null,
      title: null,
      color: null,
      filter: null,
      size: null
    }
  },
  methods: {
    showImage() {
      this.ImageUrl = `https://cataas.com/cat/gif/says/${this.title}?filter=${this.filter}&color=${this.color}&size=${this.size}`;
      console.log('url', this.ImageUrl);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top:60px;
}

html {
  background-color: rgb(134, 221, 255);
}

.image {
  height: 500px;
}

.red {
  background-color: #ff847c;
  width: 100%;
  height: 200px;
  margin-top: 50px;
  margin-bottom: 50px;
}

.btn {
margin-bottom: 50px;
}

.form-title {
margin-top: 23px;
}

</style>