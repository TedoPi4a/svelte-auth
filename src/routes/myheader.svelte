

<nav>
    <ul> 
        <div class="hamburger-lines">
            <span class="line line1"></span>
            <span class="line line2"></span>
            <span class="line line3"></span>
        </div>  

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

</nav>

<script>

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
    nav{
        background: var(--purple);
        margin: 0;
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
</style>