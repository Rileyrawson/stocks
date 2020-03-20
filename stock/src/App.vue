<template>

<div id="app">
<div id="menu">



    <div id="left">
      <router-link to="/">
        <div class="menu-item browse">
          <center>
          <i class="fas fa-home"></i>
          <p>Home</p>
          </center>
         </div>
      </router-link>

      <router-link to="/stocks">
        <div class="menu-item browse">
          <center>
          <i class="fas fa-stream"></i>
          <p>Markets</p>
          </center>
        </div>
      </router-link>
    </div>


      <div id="brand">
        <router-link to="/">
          <img src="/images/logo.png" >
        </router-link>
      </div>

    <div id="right">

      <router-link to="/search">
        <div class="menu-item browse">
          <center>
          <i class="fas fa-search"></i>
          <p>Search</p>
          </center>
        </div>
      </router-link>

      <router-link to="/compare">
        <div class="menu-item browse">
        <center>
          <i class="fas fa-balance-scale-left"></i>
          <div v-if="this.$root.$data.count < 1">
            <p>Compare</p>
          </div>
          <div v-else>
            <p>{{ count }} Stocks</p>
          </div>
          </center>
        </div>
      </router-link>
    </div>

      <div class="footer">
        <a href="https://github.com/Rileyrawson/stocks">GitHub Repository</a>
      </div>


  </div>




  <router-view />
</div>


</template>





<script>
export default {
  name: 'app',
  components: {

  },
  data() {
    return {
      product: '',
      cart: '',
    }
  },
  props:{

  },
  computed: {
    count(){
      return this.$root.$data.count;
    }
  },
  methods: {

  }
}

</script>














<style>



@media only screen and (max-width: 400px) {
#brand img {
  height:40px;
}
body {
  margin-top:5px;
}
i{
  font-size:20px;
}
#menu {
  flex-direction:column;
}

}

@media only screen and (min-width: 401px) and (max-width: 960px) {
#brand img {
  height: 70px;
}
body {
  margin-top:10px;
}
i{
  font-size:30px;
}


}

@media only screen and (min-width: 961px) {

#brand img {
  height: 110px;
}
body {
  margin-top:30px;
}
i{
  font-size:50px;
}


}






* {
  box-sizing: border-box;
}



#menu {
  display: flex;
  justify-content:center;
  align-items:center;
}

#menu a {
  color: #E4BA5E;
}

#brand {
  justify-content: center;
  padding-bottom:20px;
}



#left, #right {
  padding-bottom: 50px;
  padding:20px;
  display: flex;
  flex-direction:column;
  justify-content: space-around;
  align-items:center;
  flex-wrap: wrap;
  font-family: 'Playfair Display', serif;
}
#left{

}
#right{

}

i{
  color:#213143;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {

}

a {
  color: #E4BA5E;
  text-decoration: none;
}



.footer {
  position: fixed;
  size: 20px;
  height: 40px;
  background-color: #213143;
  font-family: 'Roboto Mono', monospace;
  color: white;
  bottom: 0px;
  left: 0px;
  right: 0px;
  margin-bottom: 0px;
  padding: 10px;
}
a:link {
  color: #F8F7F7;
}
a:visited {
  color: #F8F7F7;
}
a:hover {
  color: #B23E34;
}
</style>
