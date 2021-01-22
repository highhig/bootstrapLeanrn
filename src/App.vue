<template>
  <div id="app">

    <router-view/>
  </div>
</template>

<script>
  import AES from "./js/AES";
  export default {
    name: 'App',
    created() {
      var keys = AES.generatekey(16);
      //如果是对象/数组的话，需要先JSON.stringify转换成字符串
      let cars = ['123','456'];
      // var encrypts = AES.encrypt(JSON.stringify(cars),keys);
      // var dess = JSON.parse(AES.decrypt(encrypts,keys));
      var encrypts = AES.encrypt('zgp021020',keys);
      var dess = AES.decrypt(encrypts,keys);
      console.log(encrypts);
      console.log(encrypts.length);
      console.log(dess);
    }

  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
