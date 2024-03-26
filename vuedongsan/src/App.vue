<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <p @click="modalOpen = false">닫기</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>

  <div>
    <h1 class="red">원룸샵</h1>
  </div>

  <!-- <div v-for="(pro, i) in products" :key="i">
    <h4>{{ pro }}</h4>
    <p>{{ price[0] }} 만원</p>
  </div> -->

  <div>
    <img src="./assets/room0.jpg" class="room-img" />
    <h4 @click="modalOpen = true">{{ products[0] }}</h4>
    <p>50만원</p>
    <button @click="신고수[0] += 1">허위매물신고</button>
    <sapn>신고수 : {{ 신고수[0] }}</sapn>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>50만원</p>
    <button @click="신고수[1] += 1">허위매물신고</button>
    <sapn>신고수 : {{ 신고수[1] }}</sapn>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>50만원</p>
    <button @click="신고수[2] += 1">허위매물신고</button>
    <sapn>신고수 : {{ 신고수[2] }}</sapn>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modalOpen: false,
      신고수: [0, 0, 0],
      menus: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase() {
      this.신고수 += 1;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
