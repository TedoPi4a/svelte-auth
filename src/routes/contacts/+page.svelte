<script>
	import { initializeApp } from 'firebase/app';
    import { getFirestore, collection, addDoc, getDocs, doc, onSnapshot, getDoc  } from "firebase/firestore";

    const firebaseConfig = {
  apiKey: "AIzaSyC33HF0D6Cp6VamA_VSDzSzLXLQkg8emB8",
  authDomain: "auth-59373.firebaseapp.com",
  projectId: "auth-59373",
  storageBucket: "auth-59373.appspot.com",
  messagingSenderId: "650279718773",
  appId: "1:650279718773:web:93ae747910fa9c00f14d3c"
};

let datebase = ''


const app = initializeApp(firebaseConfig);

const db = getFirestore(app)
const colRef = collection(db, 'kur')
getDocs(colRef)
  .then((snapshot) => {
    console.log(snapshot.docs)
    let kur = []
    

    snapshot.docs.forEach((doc) => {
      kur.push({ ...doc.data(), id: doc.id})
      let user = kur[0].title
       datebase = user
    })
    console.log(kur)
  })
  .catch(err =>{
    console.log('error')
  })
    
const click = () => {
  const docRef =  addDoc(collection(db, "kur"), {
    title: newItem,
  });

  console.log("Document written with ID: ", docRef.id);

    
}   




    let newItem = '';
    let todoList = [];
	
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
    }
</script>

<input bind:value={newItem} type="text" placeholder="new todo item..">
<div>{datebase}</div>
<button class="button-6" on:click={addToList}>Add</button>
<button class="button-6" on:click={click}>Add2datebase</button>

<br/>
{#each todoList as item, index}
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
	<span class="x" on:click={() => removeFromList(index)}>✕</span>
	<br/>
{/each} 


<style> 
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
