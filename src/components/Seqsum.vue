<template>
<div> 
<Nav></Nav>
	<ul>
	<h1>seqsum </h1>
		<input v-model ="first" type="text" /> 첫번째수
		<br><br>
		<input v-model ="second" type="text" /> 두번째수
		<br><br>
		<button @click="sum">+</button>   
		<p>합계 : {{totalNum}}</p>
	</ul>
</div>
</template>
<script>
import Nav from '@/components/Nav.vue'
export default {
	name:'seqsum',
	components: {
		Nav
	},
	data(){
		return{
			totalNum:'',
			first:'',
			second:''
		}
	},
	methods:{
		sum(){
			let a = Number(this.first)
			let b = Number(this.second)
			let arr = [a, b]
			arr.sort(function (a,b) {
				return a - b
			})
			let sum = 0
			let start = Number(arr[0])
			let end = Number(arr[1])
			for(let i = start; i < end+1; i++){
				sum += i
			}
			this.totalNum = sum
		}
	}
}
</script>
<style scoped>
</style>