	<template>
		<div id="tabbar">
			<slot></slot>
		</div>
		
	</template>

	<script>	

		export default{
		name:'Tabbar',
		  components: {

		  },
			data(){
				return{

				}
			}

		};
		</script>

	<style scoped>
		#tabbar{
			display:flex;
			background-color: #f6f6f6;
			position: fixed;
			left: 0;
			right: 0;
			bottom:0;
			box-shadow: 0 -1px 1px rgba(0,0,0,.05);
			
		}
		
	</style>

