<template>
	<header>
		<h1>Task Manager</h1>
		<Button/>
	</header>
</template>
<script>
import Button from './Button.vue'
	export default {
		name: 'Header',
		components: {
			Button,
		},
		data(){
			return {
				tasks: []
			}
		},
		created(){
			this.tasks = [
			{
				id: 1,
				text: 'Buy food',
				day: 'August 1st at 8:00am',
				reminder: true
			},
			{
				id: 2,
				text: 'Doctors appointment',
				day: 'August 3rd at 12:00pm',
				reminder: true
			},
			{
				id: 3,
				text: 'Meeting at school',
				day: 'August 5th at 9:00 am'
			}
			]
		},
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