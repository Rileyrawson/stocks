<template>
<div class="wrapper">
  <div class="products">

    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <h2>{{product.symbol}}</h2>
        <p>{{product.market}}</p>
        <p>{{product.cap}}</p>
        <p>{{product.industry}}</p>
        <p>{{product.sector}}</p>
      </div>

      <div class="compare">
        <div>
          <button v-on:click='compare(product)'>Compare</button>
        </div>
      </div>
    </div>

  </div>
</div>
</template>



<script>
export default {
  name: 'ProductList',
  data() {
    return {
      product: '',

    }
  },
  props: {
    products: Array
  },
  methods: {


    compare(product){
      if (this.$root.$data.count < 1) {
        this.$root.$data.cart.pop();
      }
      this.$root.$data.cart.push(product);
      this.$root.$data.count++;
    }


  }
}
</script>





<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Playfair Display', serif;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
  display: flex;
  flex-direction: column;
}

.info {
  background: #213143;
  color: #E4BA5E;
  padding: 10px 30px;
  height: 200px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.compare {
  display: flex;
  justify-content: space-between;
}

button {
  height: 50px;
  width: 200px;
  background: #E4BA5E;
  color: #213143;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
