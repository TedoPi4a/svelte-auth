
{#if hidden}
<h1>Ur logged, good job!</h1>
<h2>very hidden stuff</h2>

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
</style>
