	<template>
		<div class="recommentd">
			<div v-for='item in recommentd' class="recommentd-item">
				<a :href="item.link">
					<img :src="item.href" alt="">	
				</a>
				<div>{{item.title}}</div>
			</div>
		</div>
	</template>

	<script>
		export default{
		name:'HomeRecommentd',
		  props:{
		  	recommentd:{
		  		type:Array,
		  		default:[],
		  	}
		  },
		  components: {

		  },
			data(){
				return{

				}
			}

		};
	</script>

	<style scoped>
		.recommentd{
			display: flex;
			width: 100%;
			text-align:cemter;
			font-size: 12px;
			padding: 10px 0 20px;
			border-bottom: 4px solid #eee
		}
		.recommentd-item{
			flex:1;

		}
		.recommentd-item img{
			width: 60px;
			height: 60px;
			border-radius: 30px;
			margin-bottom: 3px;
		}
	</style>

