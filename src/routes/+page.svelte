
{#if hidden}
<div class="bg">
    <h1>Start Your <br> Own Pyramid</h1>
    <h2>Be the boss of your own Pyramid. Achieve financial freedom.</h2>
    <button>Start Here</button>
</div>
<main class="bg2">
  <div class="price-list">
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 
     <div class="price-item">
        <div class="price">
         <h3>Free User <br>
          $0</h3> 
        </div>
        <div class="props">
          <ul>
            <li>Can not make money</li>
            <li>Can make pyramid</li>
            <li>Unlimited links</li>
          </ul> 
          <button>Join</button>
        </div>
    </div> 


    
  </div>

</main>

{:else}
<h1>You need to be logged in to acces this page</h1>
<a href="/login"><button class="button-6">Click here to log-in</button></a>

{/if}


<script>
		import {  onAuthStateChanged, getAuth } from "firebase/auth";
        import { initializeApp } from 'firebase/app';
    let hidden  
    
    const firebaseConfig = {
  apiKey: "AIzaSyC33HF0D6Cp6VamA_VSDzSzLXLQkg8emB8",
  authDomain: "auth-59373.firebaseapp.com",
  projectId: "auth-59373",
  storageBucket: "auth-59373.appspot.com",
  messagingSenderId: "650279718773",
  appId: "1:650279718773:web:93ae747910fa9c00f14d3c"
};
const app = initializeApp(firebaseConfig);
const auth = getAuth();
onAuthStateChanged(auth, (user) => {
  if (user) {
     hidden = true;
     
    // ...
  } else {
    hidden = false;

  }
});

</script>

<style>
     a{
        text-decoration: none;
        color: black;
    }
    .price-list{
      display: flex;
      justify-content: space-around;
      padding-top: 6em;  
      flex-wrap: wrap;
      position: relative;
      height: 45em;
    }
    .price-item{
      width: 10em;
      height: 0em;
      border-radius: 50%;
      margin: 0;
      padding: 0;

    }
    .props{
      background: #D9D9D9;
      display: flex;
      flex-direction: column;
      border-bottom-left-radius: 1em;
      border-bottom-right-radius: 1em;
    }
    .props ul{
      margin: 0;
      padding-left: 2em;
      padding-right: 1em;
    }
    .props ul li{
      margin: 1em 0 1em 0;
      color: var(--purple-dark);
      font-weight: 550;
    }
    .props button{
      background: linear-gradient(90.13deg, #522F4E -10.77%, #883766 104.34%);
      border: 2px solid #FFFFFF;
      box-shadow: 1px 4px 4px 2px rgba(0, 0, 0, 0.25);
      border-radius: 30px;
      width: 5.4em;
      height: 2.4em;
      text-transform: uppercase;
      margin: 0em auto 1.4em auto;
      color: white;
    }
     .price{
      background: linear-gradient(180.2deg, #683F69 -38.73%, #AC3F7F 107.5%);      
      text-align: center;
      border-top-left-radius: 1em;
      border-top-right-radius: 1em;
      height: 5em;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
     }
     .price h3{
      font-size: 1.4em;
      font-weight: 400;
     }   
    .bg{
      background-image: url(/kur.png);
      /* background-color: aqua; */
      background-position: center 65%;
      background-size: cover;
      background-repeat: repeat;
      width: 100%;
      height: 40em;
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
      flex-direction: column;
      justify-content: center;
      }
      .bg h1{
        margin: 0;
        text-align: center;
        text-transform: uppercase;
        text-shadow: 0px 4px 4px #000000;
        color: white;
        font-weight: 400;
        font-size: 7em;
        font-family: 'Roboto';
      }
      .bg h2{
        font-weight: 400;
        margin: .8em 0;
        font-size: 1.4em;
        font-family: 'Roboto';
        color: white;
        text-shadow: 3px 4px 2px rgba(0, 0, 0, 0.25);
      }
      .bg button{
        background: linear-gradient(120deg, #875382 -27.51%, #BC34AF 115.7%);
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.55);        
        border-radius: 4em;
        padding: 1em 2em; 
        text-transform: uppercase;
        color: white;
        font-size: 1em;
        border: 1px solid black;
      }
    .bg2{
        background: url(/Bg-Photo1.png);
        background-position: center ;
        background-size: cover ;
        background-repeat: no-repeat;
        width: 100%;
        height: 70em;
        

  }
</style>
