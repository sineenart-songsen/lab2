<template>
  <div id="app">
    <h1>{{ message }}</h1>
    <br />
    <span v-text="message"></span>
    <hr />

    <h1 v-show="isShow">Hello!</h1>

    <hr />
    <div v-bind:key="emp.id" v-for="emp in employees">
      {{ emp.NAME }}
      <span v-if="emp.SALARY > 90000">⭐⭐⭐</span>
      <span v-else-if="emp.SALARY >= 30000">⭐⭐</span>
      <span v-else>⭐</span>
    </div>

    <hr />
    <div v-bind:key="emp.id" v-for="emp in employees">
      <span
        v-bind:class="
          emp.SALARY > 90000 ? 'high' : emp.SALARY >= 30000 ? 'medium' : 'low'
        "
      >
        {{ emp.NAME }}
      </span>

      <span v-if="emp.SALARY > 90000">⭐⭐⭐</span>
      <span v-else-if="emp.SALARY >= 30000">⭐⭐</span>
      <span v-else>⭐</span>

      <hr />
    </div>
    <a v-bind:href="urlYT">"What Youtube</a>
    <hr />
    <img
      v-bind:src="require('@/assets/images/' + picture + '.jpg')"
      width="500px"
    />
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      picture: "pcia",
      urlYT: "https://www.youtube.com/?gl=TH",
      message: "สวัสดีจ้า",
      isShow: true,
      employees: [
        { ID: 1, NAME: "กิ๊กกาก", SALARY: 90001 },
        { ID: 2, NAME: "KIK", SALARY: 70000 },
        { ID: 3, NAME: "EIEI", SALARY: 10 }
      ]
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
.high {
  color: red;
}
.medium {
  color: green;
}
.low {
  color: blue;
}
</style>
