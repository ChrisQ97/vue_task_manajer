<template>
	<button @click="onClick()" :style="{ background: color}"> {{text}} </button>
</template>
<script>
	export default {
		name: 'Button',
		methods: {
			onClick(){
				this.$emit('toggle-add-task');
			},
		},
		props: {
			text: String,
			color: String
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

