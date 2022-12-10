<h1 style="margin: 0;">
  Users
</h1>
<!-- <input type="text" bind:value={textinput}> -->
{#await promise then guerySnapshot}
  {#each guerySnapshot.docs as doc}
    <div class="profile-container">
 
    <h1>{doc.data().name}</h1> <img src="{doc.data().img}" alt="">
    </div>
  {/each}
{/await}

<button class="button-6" on:click={f}>addtodatabase</button>
<script>
  import { initializeApp } from "firebase/app";
  import { getFirestore, collection, addDoc, getDocs, doc, getDoc, serverTimestamp } from "firebase/firestore";
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
async function f() {
  try {

console.log("Document written with ID: ", docRef.id);
} catch (e) {
console.error("Error adding document: ", e);
}}
// onMount(async () => {
// const querySnapshot = await getDocs(collection(db, "users"));
// querySnapshot.forEach((doc) => {
// msg = doc.data().name
// console.log(doc.id, " => ", doc.data());
// });
// });


</script>

<style>
      .profile-container{
        width: 8em;
        height: 2em;
        position: relative;
        display: flex;
        font-size: 1em;
        background-color: white;
        border-radius: 4em;
        justify-content: space-around;
        padding: 0 .5em;
        gap: -2em;
        margin: 1.4em 0;
        align-items: center;
    }
    .profile-container h1{
        font-size: .7em;
        /* position: absolute; */
        /* width: 1em;
        left: 0;
        top: 0; */
        
        
    }
    .profile-container img {
        border-radius: 50%;
        margin: 0;
        width: 1.5em;
    }
</style>