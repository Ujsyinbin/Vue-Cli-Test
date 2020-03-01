<template>
  <div id="app">
	  <input v-model="inputvalue" />
	  <button @click="submit">Submit</button>
	  <todo-item v-for="(value,index) in list" :key='index' :value='value' :index='index' @remove="remove(index)"></todo-item>
  </div>
</template>

<script>
import todoitem from './components/todoitem.vue'

export default {
	components:{
		'todo-item':todoitem
	},
	data:function(){
		return{
			inputvalue:'',
			list:[],
		}
	},
	methods:{
		submit(){
			this.list.push(this.inputvalue)
			this.inputvalue=''
		},
		remove(index){
			this.list.splice(index,1)
		}
	},
}
</script>

<style>
</style>
