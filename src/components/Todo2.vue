<template>
<div id="todolistapp">
<Nav></Nav>
<div id="header" class="header">
    <h2>Todo List App</h2>
	<input class="input" type="text" v-model="task" placeholder="입력 후 엔터!">
	<span class="addbutton" @click="addTodo(i)">추 가</span>
</div>
    <ul id="todolist">
	<li @click="doneToggle(todo)" v-for ="(todo, i) of todos" :key ="todo.id" :class="todo.cl" >
		<span> {{i+1}}. </span>  
		<span> {{todo.todo}} </span>  
		<span v-if="todo.cl"> (완료) </span>
		<span class="close" @click ="deleteTodo(i)"> &#x00D7; </span>
	</li>
    </ul>
</div>
</template>
<script>
import Nav from '@/components/cmm/Nav.vue'
export default {
	name:'todo2',
	components:{
		Nav
	},
	data(){
		return{todos:
		[{id:1, todo:"영화보기 ", done:false, cl:''},
		{id:2, todo:"주말산책 ", done:false, cl:''},
		{id:3, todo:"ES6 학습 ", done:false,cl:'' },
		{id:4, todo:"잠실야구장 ", done:false,cl:''}],
		task:'',
		seq:4
		}
	},
	methods:{
		addTodo(index){
			this.seq++
			this.todos.push({name:index, todo:this.task, cl:''})
            alert(this.seq)
            alert(index)
		},
		doneToggle(json){
            (json.cl=='') ? json.cl= 'checked' : json.cl = ''
		},
		deleteTodo(index){
            this.todos.splice(index ,1)
		}
	}
}

</script>
<style scoped>
 * {  box-sizing: border-box;  }
    ul {  margin: 0; padding: 0; }
    ul li {
        cursor: pointer; position: relative; padding: 8px 8px 8px 40px;
        background: #eee; font-size: 14px;  transition: 0.2s;
        -webkit-user-select: none; -moz-user-select: none;
        -ms-user-select: none; user-select: none;  
    }
    ul li:hover {  background: #ddd;  }
    ul li.checked {
        background: #BBB;  color: #fff; text-decoration: line-through;
    }
    ul li.checked::before {
        content: ''; position: absolute; border-color: #fff;
        border-style: solid; border-width: 0px 1px 1px 0px;
        top: 10px; left: 16px;  transform: rotate(45deg);
        height: 8px; width: 8px;
    }
    .close {
        position: absolute; right: 0; top: 0;
        padding: 12px 16px 12px 16px
    }
    .close:hover {
        background-color: #f44336;  color: white;
    }
    .header {
        background-color: purple; padding: 30px 30px;
        color: yellow; text-align: center;
    }
    .header:after {
        content: ""; display: table; clear: both;
    }
    .input {
        border: none; width: 75%; height:35px; padding: 10px;
        float: left; font-size: 16px;
    }
    .addbutton {
        padding: 10px; width: 25%; height:35px; background: #d9d9d9;
        color: #555; float: left; text-align: center;
        font-size: 13px; cursor: pointer; transition: 0.3s;
    }
    .addbutton:hover { background-color: #bbb; }
    .completed { text-decoration:none; }
</style>