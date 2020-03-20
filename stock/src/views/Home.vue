<template>
<div>
  <div class="wrapper">
    <div class="col">
    <div class="about">
      <h2>What Are Stocks?</h2>
      <p>Stock (also capital stock) of a corporation, is all of the shares into
        which ownership of the corporation is divided. In American English, the
        shares are collectively known as "stock". A single share of the stock
        represents fractional ownership of the corporation in proportion to the
        total number of shares. This typically entitles the stockholder to that
        fraction of the company's earnings, proceeds from liquidation of assets
        (after discharge of all senior claims such as secured and unsecured debt),
        or voting power, often dividing these up in proportion to the amount of
        money each stockholder has invested. Not all stock is necessarily equal,
        as certain classes of stock may be issued for example without voting rights,
        with enhanced voting rights, or with a certain priority to receive profits or
        liquidation proceeds before or after other classes of shareholders.</p>
      <a href="https://en.wikipedia.org/wiki/Stock">Definition from Wikipedia</a>
    </div>
    </div>
    <div class="col">
    <div class="guide">
      <h2>Stock Helper Guide</h2>

      <h3><span style="color: #E4BA5E">Stock Name: </span>The name of the company who belongs to the specific stock.</h3>
      <h3><span style="color: #E4BA5E">Stock Symbol: </span>The unique abbreviation of a company's stock that is used to identify shares of said company on a particular market.</h3>
      <h3><span style="color: #E4BA5E">Market Cap: </span>Short of Market Capitalization. Cap = Share Price * Number of Shares Outstanding.</h3>
      <h3><span style="color: #E4BA5E">Stock Market: </span>Where people buy and sell stock. The two most popular markets are the NYSE (New York Stock Exchange) and NASDAQ (National Association of Securities Dealers Automated Quotations)</h3>
      <h3><span style="color: #E4BA5E">Sector: </span>A broad classification of a part of the economy.</h3>
      <h3><span style="color: #E4BA5E">Industry: </span>Similar to a sector, but a more specific and specialized.</h3>

    </div>
    </div>
  </div>
</div>

</template>



<script>

</script>



<style scoped>


@media only screen and (max-width: 400px) {
.wrapper{
  flex-direction:column;
}
}

@media only screen and (min-width: 401px) and (max-width: 960px) {
.wrapper{
  flex-direction:row;
}
.col{
width: 50%;
}
}

@media only screen and (min-width: 961px) {
.wrapper{
  flex-direction:row;
}
.col{
width: 50%;
}
}

.wrapper{
  display: flex;
  justify-content: center;

  font-family: 'Playfair Display', serif;
}

.about{
  padding: 30px;
  padding-top: 0px;
  border: solid 5px;
  border-color: #213143;
  margin: 30px;
}

.guide{
  padding: 30px;
  padding-top: 0px;
  border: solid 5px;
  border-color: #213143;
  margin: 30px;

}


h2 {
  color: #E4BA5E;
}

h3,h4,p {
  color: #213143;
}

a {
  font-size: 10px;
  color: #213143;
}



</style>
