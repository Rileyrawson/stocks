<template>
<div>
<center>
  <div class="dropdown">
    <button class="dropbtn">Market Type:</button>
    <div class="dropdown-content">

<!--      <li class="pure-menu-item"><a @click="defaultSort()" href="#" class="pure-menu-link">Default</a></li>
      <li class="pure-menu-item"><router-link to="/stocksName">Name A-Z</router-link></li>
      <li class="pure-menu-item"><router-link to="/stocksSymbol">Symbol A-Z</router-link></li>
      <li class="pure-menu-item"><router-link to="/stocksCap">Market Cap: High-Low</router-link></li>
      <li class="pure-menu-item"><a @click="capLowHigh()" href="#" class="pure-menu-link">Market Cap: Low-High</a></li>
-->

      <li class="pure-menu-item"><a @click="marketSort('NYSE')" href="#" class="pure-menu-link">NYSE</a></li>
      <li class="pure-menu-item"><a @click="marketSort('NASDAQ')" href="#" class="pure-menu-link">NASDAR</a></li>
    </div>
  </div>

  <div class="scrollbar" id="style-default">
      <div class="force-overflow">
        <ProductList :products="products" />
      </div>
    </div>
</center>
</div>
</template>




<script>
import ProductList from "../components/ProductList.vue"

//Right now I'm trying to create a local variable called "selection"
//in order to choose which Computation is executed depending on how the data is sorted

export default {
  name: 'Browse',
  components: {
    ProductList
  },
  created(){
    this.vars = {
      selection: null
    }
  },
  data() {
    return {
      market: '',
    //  selection: '0',
    }
  },
  computed: {
    products() {
        return this.$root.$data.products.filter(product => product.market === this.market);
    }
  },
  methods: {
    marketSort(market) {
      this.vars.selection = 4;
      this.market = market;
    },
  }
}
</script>









<style>




.scrollbar
{
	margin-left: 30px;
	float: left;
	height: 600px;
	width: 90%;
	overflow-y: scroll;
	margin-bottom: 25px;
}

.force-overflow
{
	min-height: 450px;
}

#style-1::-webkit-scrollbar-track
{
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
	border-radius: 10px;
	background-color: #F5F5F5;
}

#style-1::-webkit-scrollbar
{

	background-color: #F5F5F5;
}

#style-1::-webkit-scrollbar-thumb
{
	border-radius: 10px;
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	background-color: #555;
}





/* Style The Dropdown Button */
.dropbtn {
  font-family: 'Playfair Display', serif;
  background-color: #E4BA5E;
  color: #213143;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}


.dropdown {
  list-style-type: none;
  position: relative;
  display: inline-block;
  margin-bottom: 20px;
}

.dropdown-content {
  display: none;
  position: absolute;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  font-family: 'Playfair Display', serif;
  color: #213143;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
}
</style>
