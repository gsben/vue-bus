<template>
  <div id="app">
    <!-- <firstchild class="app1"></firstchild>  -->
    <!-- <second class="app2"></second>  -->
    <router-view></router-view>
  </div>
</template>

<script>
import firstchild from './components/firstchild';
import second from './components/second';

export default {
  name: 'app',
  components:{
  	firstchild,
  	second
  }
}
</script>

<style>
 .app1{
 	border:solid green 1px;
 }
 .app2{
 	border:solid red 1px;
 }
</style>
 