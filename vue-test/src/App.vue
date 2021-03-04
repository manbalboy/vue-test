<template>
  <div id="app">
    <div>test</div>
    <div>tt</div>
    <!-- <iframe class="iframes" :src="example1Form" @load="onLoad"></iframe> -->
    <button @click="onLoad">test</button>
    {{this.example1Form }}
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      example1Form : 'https://www.inflearn.com/'
    }
  },
  methods: {
    onLoad () {
      axios.get('http://localhost:8001/').then(
        res => { 
          console.log(res);
          this.example1Form = res.data;
        })
    }
  }
}
</script>

<style>
.iframes{
  width: 1000px;
  height: 1000px;
}
</style>
