<template>
<div class="wrapper">
  <div class="stocks">

    <div class="stock" v-for="product in this.$root.$data.cart" :key="product.id">
      <div class="symbol">
        <h2>{{product.symbol}}</h2>
      </div>
      <div class="info">
        <h4>Name: {{product.name}}</h4>
        <h4>Cap:{{product.cap}}</h4>
        <h4>Market:{{product.market}}</h4>
        <p>Sector:{{product.sector}}</p>
        <p>Industry:{{product.industry}}</p>
      </div>
      <div class="price">

        <button v-on:click='remove(product)'>Remove</button>
      </div>
    </div>

  </div>
</div>
</template>


<script>
export default {
  name: 'CartList',
  data() {
    return {
      item: '',
      products: '',
      index: '',
    }
  },
  computed:  {


  },
  methods:{
    getIndex(idValue){
      for (var i = 0; i <  this.$root.$data.cart.length(); i++){
        if (this.$root.$data.cart.product.id === idValue) {
          return i;
        }
      }
    },

    remove(product){
      //var index = this.$root.$data.cart.getIndex(product.id);

      var index = this.$root.$data.cart.indexOf(product);
      this.$root.$data.cart.splice(index,1);
      this.$root.$data.count--;
    }
  },
}
</script>


<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;

}

.stocks {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  flex-direction: column;
}

.stock {
  display: flex;
  flex-direction: row;
  justify-content: space-between;

  margin: 10px;
  margin-top: 20px;
  width: 500px;
  color: #213143;
  background: #E4BA5E;
}

.symbol{
  padding-left: 10px;
}

.info {
  color: #213143;
  padding: 10px 10px;
  line-height:10px;
}

.info h1 {
  font-size: 14px;
  padding: 0px;
}

.info h4 {
  font-size: 12px;
  padding: 0px;
  line-height: 0px;
}

.info p {
  margin: 0px;
  font-size: 10px;
  padding: 0px;
}


.price {
  display: flex;
  justify-content: space-between;
}

button {
  background: #213143;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
