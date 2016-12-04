<template>
  <div class="foo">
    <p>{{foo}}</p>
    <p>{{msg}}</p>
  </div>
</template>

<script>
import Bus from '../bus.js';
export default {
  name: 'foo',
  data () {
    return {
      foo: 'Foo component',
      msg: 'this is foo data'
    }
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
<style scoped>
  .foo{
    margin: 20px auto 0;
    padding:20px;
    width: 600px;
    border:1px solid red;
  }
</style>
