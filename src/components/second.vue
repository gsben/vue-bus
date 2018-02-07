<template>
    <div id="second">
    	<h2>second</h2>
    	<p>second组件接收值{{msg}}</p>
    </div>
</template>

<script>

import bus from '../assets/eventBus';

export default {
  
  data () {
    return { 
      msg: 'world' 
    }
  },
  mounted(){
  	  var self = this;
  	  bus.$on("eventBus",function(msg){
      self.msg= msg;  
  	});
  }
}
</script>


<style>
#second{  
	width: 300px;
	height: 120px;
	border: solid green 1px;
}
</style>