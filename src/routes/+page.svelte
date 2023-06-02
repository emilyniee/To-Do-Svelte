<script>
	import ToDo from "../components/ToDo.svelte";
	
	let newToDo;
	
	let toDos = 
			[{taskName: "task 1", completed: false}, 
			{taskName: "task 2", completed: true}];
	
	function addToDo(item) {
		if (item == null) {
			alert("write a task!")
		} else {
			toDos = [...toDos, {taskName: item, completed: false}];
		}
		
	}
	
	function deleteToDo(i) {
		toDos = toDos.filter((task,index) => index !== i)
	}
	
	function checkToDo(i) {
		toDos[i].completed = !toDos[i].completed;
	}
	
</script>

<input bind:value={newToDo}>

<button on:click={()=>addToDo(newToDo)}>
	add task
</button>

{#each toDos as toDo, i}
	<ToDo taskName={toDos[i].taskName}
				completed={toDos[i].completed}/>
	<button on:click={()=>deleteToDo(i)}>
		x
	</button>
	<input type=checkbox on:click ={()=>checkToDo(i)}/>
{/each}





