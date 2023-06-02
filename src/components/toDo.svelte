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
	.completed {
		text-decoration: line-through
	}
</style>
