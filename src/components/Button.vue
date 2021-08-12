<template>
	<button @click="onClick()">Add Task</button>
</template>
<script>
	export default {
		name: 'Button',
		methods: {
			onClick(){
				console.log('soy un boton xd');
			},
		}

	}
</script>
<style>
button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>

