

<nav>
    <div class="sidebar" 	
    class:active={isHidden} on:blur={isHidden = !isHidden}>
        {#if hidden} 
        <a href="/login">
        <div class="profile-container2">
            <h1>{profilename}</h1> <img src="{profileimg}" alt="">
        </div>
        </a>
        {/if}
        <ul>
        <li>🏘️ HOME</li>
        <li>▲ MY PYRAMID</li>
        <li>CREATE A LINK</li>
        <li>MEMBERSHIPS</li>
        </ul>
    </div>
   <main>
    <ul> 
        <div class="ham" class:active2={!isHidden} on:click={() => {isHidden = !isHidden}}>
            <div class="line"></div>
            <div class="line"></div>
            <div class="line"></div>
        </div>
        <!-- <div class="hamburger-lines" >
            <span class="line line1"></span>
            <span class="line line2"></span>
            <span class="line line3"></span>
        </div>   -->

        <div class="menu-items">
        <a class="rectangle" href="/">
            <li>
                Home
            </li> 
        </a>
        <a class="rectangle" href="/date">
            <li>
                My Pyramid
            </li> 
        </a>
        
        {#if hidden} 
        <a href="/login">
        <div class="profile-container">
            
        
            <h1>{profilename}</h1> <img src="{profileimg}" alt="">
           
            
        </div>
        </a>
        {/if}
    </div>
    </ul>
</main> 
</nav>

<script>
    
	let isHidden = true
    let kur = isHidden = true
    import {  onAuthStateChanged, getAuth } from "firebase/auth";
        import { initializeApp } from 'firebase/app';
    let profilename 
    let profileimg
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
    profilename = user.displayName,
    profileimg =  user.photoURL;
    hidden = true
    // ...
  } else {
    profilename = '',
    profileimg =  '';
    hidden = false
  }
});
</script>

<style>
      .sidebar{
    position: fixed;
    width: 16em;
    top: 0;
    left: 0;
    z-index: 4;
    height: 100%;
    background-color: var(--purple-dark);
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 8em;
    justify-content:flex-start;
    gap: 2em;
    transition: all .5s ease-in-out;
}
.sidebar ul{
    display: flex;
    flex-direction: column;
    text-align: left;
}
.sidebar li{
    list-style: none;
    width: 100%;
    margin: 2em 0;
    text-align: left;
}
.profile-container2{
        width: 7em;
        height: 3.4em;
        position: relative;
        display: flex;
        font-size: 1em;
        background-color: #f1f1f1;
        border-radius: .2em;
        justify-content: space-around;
        padding: 0 .5em;
        gap: 12%;
        align-items: center;
    }
    .profile-container2 h1{
        font-size: .8em;
        /* position: absolute; */
        /* width: 1em;
        left: 0;
        top: 0; */
        margin: 0;
        
    }
    .profile-container2 img {
        border-radius: 50%;
        margin: 0;
        width: 2.1em;
        border: 1px solid #875382;

    }
.line{
        width: 1.2em;
  height: 4.5px;
  background-color: #ecf0f1;
  display: block;
  margin: 8px auto;
  -webkit-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
    border-radius: 4em;
  }
  .ham.active2 .line:nth-child(2){
    opacity: 0;
  }
  
  .ham.active2 .line:nth-child(1){
    -webkit-transform: translateY(13px) rotate(45deg);
    -ms-transform: translateY(13px) rotate(45deg);
    -o-transform: translateY(13px) rotate(45deg);
    transform: translateY(13px) rotate(45deg);
  }
  
  .ham.active2 .line:nth-child(3){
    -webkit-transform: translateY(-13px) rotate(-45deg);
    -ms-transform: translateY(-13px) rotate(-45deg);
    -o-transform: translateY(-13px) rotate(-45deg);
    transform: translateY(-13px) rotate(-45deg);
  }
  .ham{
    position: relative;
    cursor: pointer;
    margin-left: .4em;
    
  }
.active2{
    /* transform: rotate(-180deg); */
    -webkit-transition: all 1s ease-in-out;
  -moz-transition: all .1s linear;
  -o-transition: all .1s linear;
  transition: all .5s ease-in-out;
  opacity: 1;
  
  }
.active{
        background-color: var(--purple);
        left: -17em;
        transition: all .5s ease-in-out;
    }


    main{
        background: var(--purple);
        margin: 0;
        width: 100%;
        z-index: 49;
        position: fixed;
    }
    .hamburger-lines .line {
        width: 1em;
        height: 0;
        margin: .1em 0;
  border: 2px solid #FFFFFF;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
}
    .hamburger-lines {
   margin-left: 1em;
   z-index: 9;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

    .login-button a{
        text-decoration: none;
        color: black;
        font-size: 1.4em;
    }
    .login-button1 a{
        text-decoration: none;
        color: black;
        font-size: 1;
        text-align: center;
    }
    .login-button1{ 
        width: 12em;
        text-align: center;
    }
    nav ul{
        margin: 0;
        padding: 0;
        display: flex;
        list-style: none;
        justify-content: space-between;
        font-size: 2em;
        height: 1.6em;
        align-items: center;
    }
    ul li a{
        color: white;
        text-decoration: none;  
        font-weight: 400;
        font-size: .6em;
        text-align: center;
        position: relative;
    }
    a{
        text-decoration: none;
        color: black;
    }
    .menu-items{
        display: flex;
        align-items: center;
        justify-content:space-around;
        margin-right: 1em;
        gap: 1em;
    }
    .rectangle{
        background: var(--purple-dark);
        text-decoration: none;
        border-radius: 25px;
        width: fit-content;
        padding: 0 .6em;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 1.2em;
        text-transform:uppercase;
    }
    li {
        font-size: .5em;
        color: white;
    }
    .profile-container{
        width: 3em;
        height: 1.4em;
        position: relative;
        display: flex;
        font-size: 1em;
        background-color: #f1f1f1;
        border-radius: .2em;
        justify-content: space-around;
        padding: 0 .5em;
        gap: 12%;
        align-items: center;
    }

    .profile-container h1{
        font-size: .4em;
        /* position: absolute; */
        /* width: 1em;
        left: 0;
        top: 0; */
        margin: 0;
        
    }
    .profile-container img {
        border-radius: 50%;
        margin: 0;
        width: 1.1em;
        border: 1px solid #875382;

    }
    @media screen and (max-width: 780px) {
.profile-container{
    visibility: hidden;
}
.menu-items{
    visibility: hidden;
}
}
</style>