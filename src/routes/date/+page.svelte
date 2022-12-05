<h1>
    this is for datebase
</h1>
<button class="button-6" on:click={f}>addtodatabase</button>
<p>{msg}</p>
<button class="button-6" >addtodatabase</button>
<script>
    import { initializeApp } from "firebase/app";
    import { getFirestore, collection, addDoc, getDocs, doc, getDoc } from "firebase/firestore";
	import { onMount } from 'svelte';
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
let msg 
async function f() {
    try {
  const docRef = await addDoc(collection(db, "users"), {
    first: "me",
    last: "Lovelace",
    born: 1815
  });
  console.log("Document written with ID: ", docRef.id);
} catch (e) {
  console.error("Error adding document: ", e);
}}
onMount(async () => {
    
    const docRef = doc(db, "users", 'HL9J9mSKxbAoy648WWxg' );
    const docSnap = await getDoc(docRef);

if (docSnap.exists()) {
  console.log("Document data:", docSnap.data());
  msg = 'Ime: ' + docSnap.data().name + ' Age: ' + docSnap.data().age
} else {
  // doc.data() will be undefined in this case
  console.log("No such document!");
}
})

</script>