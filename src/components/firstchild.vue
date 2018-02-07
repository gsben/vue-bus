<template>
    <div id="firstchild" v-show='flags'>
    	<h2>firstchild</h2>
      <p>{{mssg}}</p>
      <button v-on:click='sendMsg'>firstchild组件传值</button>
    </div>
</template>

<script>
import bus from '../assets/eventBus';

export default {
  
  data () {
    return {
      mssg:'',
      flags:true
    }
  }, 
  mounted(){
    var self = this;
    bus.$on("event",function(data){
       self.mssg = data;
    });
  },
  methods:{
    sendMsg:function(){
      bus.$emit('eventBus',' 欢迎来到gsben的博客');
      // this.flags = false;
      // this.$router.push('/second');
    }
  },
}
</script>

<style type="text/css">
  #firstchild{ 
    width: 400px;
    height: 140px;
    border:solid blue 1px;
  }
</style>

