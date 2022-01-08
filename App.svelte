<style>
	button{background:#FFC0CB;
	color:#FFFFFF;
	left:50%;
	right:50%;
	}
	:global(body) {
		background-color: #A5E5FA;
		opacity:0.8;
	}
	input{left:50%;
	right:50%;
	}
	
</style>
<script>
	let todos=[];
	
	function addToDo(){
		todos=[...todos,''];
	}
	function removeSelf(index){
		todos=[...todos.slice(0,index),...todos.slice(index+1)];
	}
	
</script>
<p>
	Task for the day:
</p>
{#each todos as todo, index}
<input bind:value={todos[index]} placeholder="Enter Task">
<button on:click={()=>removeSelf(index)}>X
</button>


<br>
{/each}

<button on:click={addToDo} >Add</button>
