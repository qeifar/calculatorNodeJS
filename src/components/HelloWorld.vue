<template>
  <!-- <div class="hello">
    <h1>{{ msg }}</h1> -->
 <div id="calculator">
	<div class="container">
		<form action="">
			<h1>The Car-culator</h1>
			<p>Discover your monthly car payment</p>
			<label for="price">Purchase price</label>
			<input type="number" name="price" class="currency" v-model.number="price"/>
			<br />
			<label for="down-payment">Down payment</label>
			<input type="number" name="down-payment" class="currency" v-model.number="downPayment"/>
			<br />
			
			<label for="trade-in">Trade-in value</label>
			<input type="number" name="trade-in" class="currency" v-model.number="tradeIn"/>
			<br />
			
			<label for="length">Term length</label>
			<select name="length" v-model="length">
				<option value="12">12 months</option>
				<option value="24">24 months</option>
				<option value="36">36 months</option>
				<option value="48">48 months</option>
				<option value="60" selected>60 months</option>
				<option value="72">72 months</option>
				<option value="84">84 months</option>
			</select>
			
			<label for="rate">Rate</label>
			<input type="number" name="rate" v-model.number="rate"/>
		</form>
		<div class="payment">{{ calcPayment }} / month</div>
	</div>
</div>

  <!-- </div> -->
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}


// var calculator = new Vue({
// 	el: '#calculator',
// 	data: {
// 		price: '',
// 		downPayment: '',
// 		tradeIn: '',
// 		length: '60',
// 		rate: '',
// 		calcPayment: ''
// 	},
// 	computed: {
// 		calcPayment: function(e){
// 			var p = this.price - this.downPayment - this.tradeIn;
// 			var r = this.rate / 1200;
// 			var n = this.length;
// 			var i = Math.pow((1+r),n);
// 			var payment = ( p * r * i) / (i - 1) || 0;
// 			return currencyFormat(payment);
// 		},
// 		numFormat: function(e){
// 			e.replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
// 		}
// 	}
	
// });


 //https://blog.tompawlak.org/number-currency-formatting-javascript
 function currencyFormat (num) {
     return "$" + num.toFixed(0).replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,")
 }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
 * {
	box-sizing: border-box;
}

html {
	font-family: "proxima-nova", "Helvetica Neue",Helvetica,Arial,sans-serif;
	-webkit-font-smoothing: antialiased;
}

body {
	background-image: linear-gradient( #3200ff, #00ff7e );
	height: 100vh;
	display: flex;
	align-items: center;
	flex-direction: column;
	justify-content: center;
	padding-top: 16px;
	transition: all 0.3s ease-in;
	
	@media (max-width: 512px){
		padding: 32px;
		transition: all 0.3s ease-in;
	}
	
	@media (max-width: 360px){
		padding: 16px;
		transition: all 0.3s ease-in;
	}
	
}

h1 {
	text-align: center;
	color: #000;
	margin: 0 0 16px 0;	
}

p {
	text-align: center;
	margin-top: 0;
	margin-bottom: 24px;
}

.container {
	max-width: 480px;
	margin: 0 auto;
	background-color: #fff;
	padding: 64px;
	box-shadow: 2px 2px 96px #111;
	border-radius: 8px;
	transition: all 0.3s ease-in;
	
	@media (max-width: 512px){
		padding: 32px;
		transition: all 0.3s ease-in;
	}
	
	@media (max-width: 360px){
		padding: 16px;
		transition: all 0.3s ease-in;
	}
	
}

label {
	display: inline-block;
	width: 25%;
	min-width: 128px;
	margin-bottom: 8px;
	font-weight: bold;
}

input, select {
	display: inline-block;
	background-color: #fff;
	color: #888;
	border: 2px solid #888;
	border-radius: 2px;
	height: 56px;
	width: 100%;
	font-size: 24px;
	padding: 0 16px;
	margin-bottom: 24px;
	
	&:focus {
		background-color: #fff;
		color: #3200ff;
		border-color: #3200ff;
		outline: 0;
	}
	
}

input[type=number]::-webkit-inner-spin-button, 
input[type=number]::-webkit-outer-spin-button { 
  -webkit-appearance: none; 
  margin: 0; 
}

.payment {
	color: #000;
	font-size: 48px;
	text-align: center;
	font-weight: bold;
	transition: all 0.3s ease-in;
	
	@media (max-width: 512px){
		font-size: 40px;
		transition: all 0.3s ease-in;
	}
	
	@media (max-width: 400px){
		font-size: 32px;
		transition: all 0.3s ease-in;
	}
	
}

@media (max-height: 750px){
	body {
		height: 100%;
	}
} 

/* h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>
