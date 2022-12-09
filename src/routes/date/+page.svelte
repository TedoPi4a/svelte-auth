<h1>
  this is for datebase
</h1>
<input type="text" bind:value={textinput}>
{#await promise then guerySnapshot}
  {#each guerySnapshot.docs as doc}
    <li>{doc.data().name}</li>
  {/each}
{/await}

<button class="button-6" on:click={f}>addtodatabase</button>
<button class="button-6" >addtodatabase</button>
<script>
  import { initializeApp } from "firebase/app";
  import { getFirestore, collection, addDoc, getDocs, doc, getDoc, serverTimestamp } from "firebase/firestore";
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
const getQuerySnapshot = async () => {
  return await getDocs(collection(db, "users"));
}

let promise = getQuerySnapshot ();
let msg 
let textinput
async function f() {
  try {
const docRef = await addDoc(collection(db, "users"), {
  name: textinput,
});
console.log("Document written with ID: ", docRef.id);
} catch (e) {
console.error("Error adding document: ", e);
}}
onMount(async () => {
const querySnapshot = await getDocs(collection(db, "users"));
querySnapshot.forEach((doc) => {
// doc.data() is never undefined for query doc snapshots
msg = doc.data().name
console.log(doc.id, " => ", doc.data());
});
});


</script>