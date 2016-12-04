<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <bar></bar>
    <foo></foo>
  </div>
</template>

<script>
import foo from "./components/Foo.vue";
import bar from "./components/Bar.vue";
import Bus from './bus.js';
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to App'
    }
  },
  components:{
    foo,
    bar
  },
  mounted:function(){
    var _this=this;
    Bus.$on('add',function(msg){
      _this.msg=msg;
      console.log(_this.msg);
    });
  },
  methods:{
    
  },
  events:{

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
  margin: 50px;
}
input{
    padding: 5px 10px;
}
</style>
