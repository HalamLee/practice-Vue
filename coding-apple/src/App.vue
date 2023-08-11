<template>
  <div class="black-bg" v-if="modalState" @click.self="modalState = false">
    <div class="white-bg">
      <h4>{{ modalData.title }}</h4>
      <p>{{ modalData.content }}</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <div v-for="(product, idx) in data" :key="product.id">
    <img :src="product.image" class="room-img" />
    <h4 @click="modalClickHandler(product)">{{ product.title }}</h4>
    <p>{{ product.price }}원</p>
    <button @click="increase(idx)">허위매물신고</button>
    <span>신고수: {{ reportNum[idx] }}</span>
  </div>
</template>

<script>
import data from './data/data';

export default {
  name: 'App',
  data() {
    return {
      modalState: false,
      modalData: { title: '', content: '' },
      reportNum: new Array(data.length).fill(0),
      menus: ['Home', 'Shop', 'About'],
      data,
    };
  },
  methods: {
    increase(idx) {
      this.reportNum[idx] += 1;
    },
    modalClickHandler(product) {
      this.modalState = true;
      this.modalData = { title: product.title, content: product.content };
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

h4 {
  cursor: pointer;
}
</style>
