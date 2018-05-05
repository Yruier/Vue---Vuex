<template>
  <div id="app">
    <Head :tit="title"></Head>
    <div class="section">
	    	<Location></Location>
	      <Product></Product>
    </div>
    <Foot></Foot>
  </div>
</template>

<script>
	import './common/fonts(1)/iconfont.css';
	import './common/add&del/iconfont.css'
	import Head from './components/header/Header.vue';
	import Location from './components/section/location/Location.vue';
	import Product from './components/section/product/Product.vue';
	import Foot from './components/footer/Footer.vue'
	export default {
	  name: 'App',
	  data () {
	    return {
					title: "订单支付"
	    }
		},
	  components: {
	    Head,
	    Location,
	    Product,
	    Foot
	  }
	}
</script>

<style>
	*{
	  padding: 0;
	  margin: 0;
	  list-style: none;
	  text-decoration: none;
	}
	
	body,html {
		 width: 100%;
	   height: 100%;
	   background: #EEEEEE;
	}
	
	#app {
	  font-family: 'Avenir', Helvetica, Arial, sans-serif;
	  -webkit-font-smoothing: antialiased;
	  -moz-osx-font-smoothing: grayscale;
	  color: #2c3e50;
	  width: 100%;
	  height: 100%;
	  background: #EEEEEE;
	  display: flex;
	  flex-direction: column;
	}

	.section {
		overflow-y:scroll;
	}

</style>


