<template>
<div>
<Nav></Nav>
<div id="example" class="container layout1">
	<h2>계좌 개설 </h2>
    <p><input type="text" v-model="amount" class="form-control" /></p>
    <p>
        <button id="create" @click.once="specialEvent"
           class="btn btn-primary">계좌 개설 10000원 이벤트 </button>
        <button id="deposit" @click="deposit($event)"
            class="btn btn-primary">예금 </button>
        <button id="withdraw" @click="withdraw"
            class="btn btn-primary">인출 </button>
        <button id="clear" @click="clear"
            class="btn btn-primary">청소  </button>
    </p>            
    <h3>계좌 잔고 : {{balance}}</h3>
</div>
</div>
</template>
<script>
import Nav from '@/components/cmm/Nav.vue'
export default {
	name:'account',
	components:{
		Nav
	},
	data(){
		return{
			amount:'',
			balance:0
		}
	},
	methods:{
		specialEvent(){
			this.balance = 10000
		},
		deposit(){
			this.balance += Number(this.amount)
		},
		withdraw(){
			this.balance -= Number(this.amount)
		},
		clear(){
			this.balance = 0
		}
	}
}
</script>
<style scoped>
  .layout1 { margin:30px 30px 30px 30px; }
</style>