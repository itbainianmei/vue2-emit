<template>
  <div class="bar">
    <p>{{bar}}</p>
    <form v-on:submit.prevent="add">
        <input type="text" v-model="msg">
        <input type="submit" value="add">
    </form>
  </div>
</template>

<script>
import Bus from '../bus.js';
export default {
  name: 'bar',
  data () {
    return {
      bar: 'Bar component',
      msg: 'this is bar data'
    }
  },
  mounted:function(){
    
  },
  methods:{
    add(){
      Bus.$emit('add',this.msg);
      this.msg='';
    }
  },
  events:{

  }
}
</script>
<style scoped>
    .bar{
        margin: 20px auto 0;
        padding:20px;
        width: 600px;
        border:1px solid red;
    }
</style>
