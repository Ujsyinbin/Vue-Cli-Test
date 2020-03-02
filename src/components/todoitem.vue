<template>
	<div @mouseenter="dealshow(true)" @mouseleave="dealshow(false)" :style="{background:bgcolor}">
		{{value.inputvalue1|addValueUnit}}
		{{value.inputvalue2}}
		<button v-show="ischoose" @click="remove">remove</button>
	</div>
</template>

<script>
	export default {
		props:['value','index'],
		data(){
			return {
				bgcolor:'#fff',
				ischoose: false
			}
		},
		methods: {
			dealshow(flag){
				this.bgcolor = flag?'#bcbcbc' : '#fff'
				this.ischoose = flag
			},
			remove(){
				this.$emit('remove',this.index)
			},
		},
		filters:{
			addValueUnit(value){
				return value+" 和"
			}
		}
	}
</script>

<style scoped>
</style>
