<template>
<div>
<header class="header" role="banner">
        <div class="div1">
            <img style = "width:50px;height:50px;" :src="img" alt="">
				<div>
               <nav class="nav">
                  <a class="login">Login</a>
                  <a class="join">Join</a>
                  <a class="mypage">Mypage</a>
                  <a class="logout">Logout</a>
               </nav>
				
				</div>
        </div>

</header>

<br><br><br><br><br><br><br><br><br><br>
<Nav></Nav>
</div>
</template>

<script>
import Nav from '@/components/cmm/Nav.vue'
export default {
	name: 'navbar',
	components: {
		Nav
	},
	data(){return {img: require(`@/assets/images/pencil.jpg`)
}}
}

</script>

<style scoped>
.header{
	background-color: #1C1C1C;
}
.div1{
   width: 100%;
   height: 100%;
   font-size: 30px;
}
.nav{
	width:100px ;
	height:50px;
}
a {
	color: white;
	margin-right:16px!important;
	text-align: center;
	font-family:Arial;
}
a:active{
      color:red;
      }
</style>