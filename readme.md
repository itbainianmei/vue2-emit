## vue2.0 单一事件管理组件通讯

## bus.js
```bash
#bus.js
import Vue from "vue";
export default new Vue();
```

## foo.vue
```bash
#foo.vue
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
  }
}
```

## bar.vue
```bash
#bar.vue
import Bus from '../bus.js';
export default {
  name: 'bar',
  data () {
    return {
      bar: 'Bar component',
      msg: 'this is bar data'
    }
  },
  methods:{
    add(){
      Bus.$emit('add',this.msg);
      this.msg='';
    }
  }
}
```

```bash
npm install

npm  run dev
```