<template>
	<div>
	{{value}}
	<button @click="remove">remove</button>
	</div>
</template>

<script>
	export default {
		props:['value','index'],
		methods: {
			remove(){
				this.$emit('remove',this.index)
			}
		}
	}
</script>

<style>
</style>
