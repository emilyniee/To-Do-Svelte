<script>
	export let taskName, completed;
</script>

{#if completed}
<h1 class = "completed">
		{taskName}
	</h1>
{:else}
	<h1>
		{taskName}
	</h1>
{/if}

<style>
	* {
		font-size: 16px;
		font-weight: 100;
	}

	h1 {
		padding: 8px;
		padding-left: 0;
	}

	.completed {
		text-decoration: line-through
	}
</style>
