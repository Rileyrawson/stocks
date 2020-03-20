<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search fa-lg"></i><input v-model="searchText" placeholder="Search by Company Name"/>
      </form>
    </div>
  </div>
  <div class="scrollbar" id="style-default">
      <div class="force-overflow">
        <ProductList :products="products" />
      </div>
    </div>
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"


export default {
  name: 'Home',
  components: {
    ProductList,
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    products(){
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText) >= 0);
    },


    nameSearch() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText) >= 0);

    },
    symbolSearch(){
      return this.$root.$data.products.filter(product => product.symbol.toLowerCase().search(this.searchText) >= 0);
    }

  }
}
</script>





<style scoped>


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












::placeholder {
  color: #949494;
}

.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Playfair Display', serif;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
  margin-bottom:20px;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

.fas fa-search {
  font-size: 10px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
