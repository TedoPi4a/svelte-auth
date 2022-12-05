

<nav>
    <ul> 
        <li>
            <a href="/">Home</a>
        </li>
        <li>
            <a href="/login">Log-in</a>

        </li>
        <li>
            <a href="/contacts">Contacts</a>

        </li>
        <li>
            <a href="/date">DB</a>

        </li>
        {#if hidden} 
        <div class="profile-container">
            
        
            <h1>{profilename}</h1> <img src="{profileimg}" alt="">
           
            
        </div>
        {/if}
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
        background-color: gray;
        margin: 0;
        
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
        display: flex;
        list-style: none;
        justify-content: space-around;
        font-size: 2em;
        height: 1.5em;
        align-items: center;
    }
    ul li a{
        color: white;
        text-decoration: none;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    .profile-container{
        width: 3em;
        height: 1.4em;
        position: relative;
        display: flex;
        font-size: 1em;
        background-color: white;
        border-radius: .1em;
        justify-content: space-around;
        padding: 0 .5em;
        gap: -1em;
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
    }
</style>