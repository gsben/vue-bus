<template>
    <div>
    	{{number}}
    	<button v-on:click='sendMsg'>随机增加</button>
    </div>
</template>

<script>
export default {
  props:{
     number:{
     	type:Number
     }
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
  	sendMsg:function(){
  		const num = Math.floor(Math.random()*100+1);
  		this.$bus.emit('add',num);
  	}
  }
}
</script>

<style type="text/css">
  #firstchild{ 
    width: 400px;
    height: 300px;
    border:solid red 1px;
  }
</style>

