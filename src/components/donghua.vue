<template>
    <div id="thirdchild">
      <div  v-show='aa'>
      	<h2>donghua</h2>
      	<p>{{msg}}</p>
        <button @click='action'>点击事件</button>
      </div>
      <first v-show='flag'></first>
      <second v-show='flag'></second>
    </div>
</template>

<script>
import bus from '../assets/eventBus'

import first from './firstchild'
import second from './second'


export default {
  components:{
    first,
    second
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      flag: true,
      aa:true
    }
  },
  methods:{
     action:function(){
      // this.$router.push('/firstchild');
      bus.$emit('event','hello guo');
      // this.flag = true;
      // this.aa = true;
    },

  },
  mounted(){
    /*var self = this;
    bus.$on("eventBus",function(msg){
      self.msg= msg; 
      alert(self.msg+"993");
    });*/
  }
}
</script>

<style type="text/css">
  #thirdchild{
    width: 400px;
    height: 300px;
    border:solid red 1px;
  }
</style>

