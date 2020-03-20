  <template>
<div>
  <div class="wrapper">
    <div class="title">
      <h2>Compare</h2>
    </div>

    <div class="print">
      <div v-if="this.$root.$data.count < 1">
        <h3>Nothing to Compare! Find stocks you want to compare by browsing the
          <router-link to="/Stocks">Stocks</router-link>
          page or by
          <router-link to="/search">Searching</router-link>
          for specific companies</h3>
      </div>
      <div v-else>
        <CartList :products="products" />
      </div>
    </div>

  </div>

</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Cart',
  components: {
    CartList
  },
  data() {
    return {

    }
  },

  methods: {

  },

  computed: {
    print() {
      return this.$root.$data.cart;
    }
  },


}
</script>


<style scoped>

h2 {
  color: #213143;
  text-align: center;
  font-size: 40px;
}

.print{
  margin-bottom: 100px;
  margin-right: 100px;
  margin-left: 100px;
  padding: 10px;
  border-style: solid;
  border-width:5px;
  border-color: #fff;
}

h3 {
  color: #213143 ;
  text-align: center;
  font-size: 30px;

}

.wrapper{
  font-family: 'Playfair Display', serif;
}

a {
  color: #E4BA5E;
  text-decoration: none;
}

a:active {
  text-decoration: underline;
}

a:hover {
  text-decoration: underline;
}
</style>
