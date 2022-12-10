<!-- <script>
  const stripe = require('stripe')('sk_test_51MDWWLJEKT4p5uDp6Lt7LlmEwbhfX78fkHtmDervvk8Y68EykcWIl2Vne6BsaaKJo57hgBBlceho3fR5UnNAMdBF00ArxvBYen');
const express = require('express');
const app = express();
app.use(express.static('public'));

const YOUR_DOMAIN = 'http://localhost:4242';

app.post('/create-checkout-session', async (req, res) => {
  const session = await stripe.checkout.sessions.create({
    line_items: [
      {
        // Provide the exact Price ID (for example, pr_1234) of the product you want to sell
        price: '{{PRICE_ID}}',
        quantity: 1,
      },
    ],
    mode: 'payment',
    success_url: `${YOUR_DOMAIN}/success.html`,
    cancel_url: `${YOUR_DOMAIN}/cancel.html`,
  });

  res.redirect(303, session.url);
});

app.listen(4242, () => console.log('Running on port 4242'));
  </script> -->


<h1>Kupi si neshto, Rosene</h1>
<section>

  <div class="product-card">
		<div class="product-tumb">
			<img src="/bhs_cover.png" alt="">
		</div>
		<div class="product-details">
			<h4><a href="">Nqkva mizerna pesen</a></h4>
			<p>ne znam kupi si cmon man</p>
			<div class="product-bottom-details">
				<div class="product-price">20leva</div>
				<div class="product-links">
					
          <a href="https://buy.stripe.com/test_4gwaHsgPCcvbf0Q000"><button class="fa fa-shopping-cart, button-6">Buy Now</button></a>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto:400,500,700');
*
{
    -webkit-box-sizing: border-box;
            box-sizing: border-box;
    margin: 0;
    padding: 0;
}
button{
  width: 6em;
}

body
{
    font-family: 'Roboto', sans-serif;
}
a
{
    text-decoration: none;
}
.product-card {
    width: 20em;
    position: relative;
    box-shadow: 0 2px 7px #dfdfdf;
    margin: 50px auto;
    background: #fafafa;
    border-radius: 1em;
}



.product-tumb {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1em;
    background: #f0f0f0;
}

.product-tumb img {
    max-width: 100%;
    max-height: 100%;
}

.product-details {
    padding: 30px;
}

.product-catagory {
    display: block;
    font-size: 12px;
    font-weight: 700;
    text-transform: uppercase;
    color: #ccc;
    margin-bottom: 18px;
}

.product-details h4 a {
    font-weight: 500;
    display: block;
    margin-bottom: 18px;
    text-transform: uppercase;
    color: #363636;
    text-decoration: none;
    transition: 0.3s;
}



.product-details p {
    font-size: 15px;
    line-height: 22px;
    margin-bottom: 18px;
    color: #999;
}

.product-bottom-details {
    overflow: hidden;
    border-top: 1px solid #eee;
    padding-top: 20px;
    display: flex;
    align-items: center;
    justify-content: space-around;
}

.product-bottom-details div {
    float: left;
    width: 50%;
}

.product-price {
    font-size: 1.4em;

    color: #000000;
    font-weight: 600;
}



.product-links {
    text-align: right;
}

.product-links a {
    display: inline-block;
    margin-left: 5px;
    color: #e1e1e1;
    transition: 0.3s;
    font-size: 17px;
}

.product-links a:hover {
    color: #fbb72c;
}
.checked {
        text-decoration: line-through;
    }
    input{
        border-radius: 2em;
        padding: .2em 1em;
    }
    .x{
        cursor: pointer;
    }
</style>