<template>
	<header>
		<h1>Task Manager</h1>
		<Button @toggle-add-task="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'"/>
	</header>
</template>
<script>
import Button from './Button.vue'
	export default {
		name: 'Header',
		components: {
			Button,
		},
		props: {
			showAddTask: Boolean,
		}
		
	}
</script>

<style scoped>
header	{
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 20px;
}
</style>