
<div class="text-column">
  {#if !hidden}
  <h1>Log-in, sir</h1>
  {:else}
  <h1> Hey, {guz}   <img src="{src}" alt=""></h1> 

  {/if}
  {#if !hidden}
	<button class="button-6" on:click={loginGoogle}>Google</button>
	<button class="button-6" on:click={Facebook}>Facebook</button>
  {:else}
	<button class="button-6" on:click={out}>Log out</button>
  {/if}

	</div>
	
	<script>
		import { getAuth, GoogleAuthProvider, signInWithPopup, onAuthStateChanged, signOut, FacebookAuthProvider  } from "firebase/auth";
		import { initializeApp } from 'firebase/app';
    import { getFirestore, collection, addDoc, getDocs, doc, getDoc, serverTimestamp } from "firebase/firestore";

        import { redirect } from '@sveltejs/kit';

    let guz = 'Hey,';
    let src = '';
    let hidden = false;
    const provider = new GoogleAuthProvider();


const firebaseConfig = {
  apiKey: "AIzaSyC33HF0D6Cp6VamA_VSDzSzLXLQkg8emB8",
  authDomain: "auth-59373.firebaseapp.com",
  projectId: "auth-59373",
  storageBucket: "auth-59373.appspot.com",
  messagingSenderId: "650279718773",
  appId: "1:650279718773:web:93ae747910fa9c00f14d3c"
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);




const loginGoogle = () => {
  const auth = getAuth();
signInWithPopup(auth, provider)
  .then((result) => {
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    // The signed-in user info.
    const user = result.user;
    const uid = user.uid;
    const docRef = addDoc(collection(db, "users"), {
  name: user.displayName,
  img : user.photoURL
});
    // ...
  }).catch((error) => {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;
    // The email of the user's account used.
    const email = error.customData.email;
    // The AuthCredential type that was used.
    const credential = GoogleAuthProvider.credentialFromError(error);
    // ...
  });}

const auth = getAuth();

const out = () => {
    const auth = getAuth();
  signOut(auth).then(() => {
}).catch((error) => {
  // An error happened.
});
}

const Facebook = () => {
  const auth = getAuth();
  const provider = new FacebookAuthProvider();
signInWithPopup(auth, provider)
  .then((result) => {
    
    const user = result.user;

    // This gives you a Facebook Access Token. You can use it to access the Facebook API.
    const credential = FacebookAuthProvider.credentialFromResult(result);
    const accessToken = credential.accessToken;

    // ...
  })
  .catch((error) => {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;
    // The email of the user's account used.
    const email = error.customData.email;
    // The AuthCredential type that was used.
    const credential = FacebookAuthProvider.credentialFromError(error);

    // ...
  });


}

onAuthStateChanged(auth, (user) => {
  if (user) {
    guz = user.displayName;
    src = user.photoURL;
     hidden = true;

    // ...
  } else {
    guz = '';
    src = '';
    hidden = false;

  }
});

	</script>
	
<style>
	input{
		margin-top: 2em;
		width: 23em;
		border-radius: 2em;
		padding-left: 1em;
		
		}

h1 img{
  border-radius: 50%;
  width: 1.6em;
  position: absolute;
  margin-left: .4em;
  
}
h1{
    position: relative;
}

</style>

