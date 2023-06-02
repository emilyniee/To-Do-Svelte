<script>
	import ToDo from "../components/ToDo.svelte";
	
	let newToDo;
	
	let toDos = 
			[];
	
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

<div class="whole">
	<h1>
		TO DO LIST
	</h1>

	<input bind:value={newToDo}>

	<button on:click={()=>addToDo(newToDo)}>
		add task
	</button>

	<div class="todo-list">
		{#each toDos as toDo, i}
			<div class="todo">
				<ToDo taskName={toDos[i].taskName}
							completed={toDos[i].completed}/>
				<button on:click={()=>deleteToDo(i)}>
					x
				</button>
				<input type=checkbox on:click ={()=>checkToDo(i)}/>
			</div>
		{/each}
		
	</div>
</div>

<style>
	* {
		font-family: Arial, Helvetica, sans-serif;
		font-size: 16px;
	}

	.whole {
		margin: 16px;
	}

	.todo {
		display: flex;
	}

	button {
		background: none;
		border-style: none;
	}

</style>



