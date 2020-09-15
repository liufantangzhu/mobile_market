<template>
	<div class="navbar">
		<div class='left' >
			<slot name='left'></slot>
		</div>
		<div class='center'>
			<strong>
				<slot name='center'></slot>
			</strong>			
		</div>
		<div class='right'>
			<slot name='right'></slot>
		</div>
	</div>
</template>

<script>
	export default{
	name:'Navbar',
	  components: {

	  },
		data(){
			return{

			}
		}

	};
</script>

<style scoped>
	.navbar{
		display:flex;
		height: 44px;
		line-height: 44px;
		text-align: center;
		
	}
	.left, .right {
		width: 60px;
	}
	.center{
		flex: 1;
		font-family: Avenir, Helvetica, Arial, sans-serif;
	  -webkit-font-smoothing: antialiased;
	  -moz-osx-font-smoothing: grayscale;
	  text-align: center;
	  color: #ffffff;
	}
</style>

