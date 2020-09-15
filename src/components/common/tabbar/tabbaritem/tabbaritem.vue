	<template>
		<div class="tabbar-item" @click='itemClick'>
			<div v-if="isactive">
				<slot name='item-icon'></slot>
			</div>
			<div v-else>
				<slot name='item-active'></slot>
			</div>
			<div :style='actilveStyle'>
				<slot  name='item-text'></slot>
			</div>
			
			
		</div>
	</template>

	<script>
		export default{
		name:'TabbarItem',
		props:{
			path:String,
			activecolor:{
				type:String,
			}
		},
			data(){
				return{

				}
			},
			computed:{
				isactive(){
					return this.$route.path.indexOf(this.path)
				},
				actilveStyle(){
					return this.isactive?{color:this.activecolor}:{color:'rgb(255, 181, 206)'}
				}
			},
			methods:{
				itemClick(){
					this.$router.replace(this.path)
				}
			}

		};
	</script>

	<style lang="scss" scoped>
		.tabbar-item{
			flex:1;
			text-align:center;
			height:49px;
			font-size:14px;

			img {
				width: 24px;
				height: 24px;
				margin-top:3px;
				vertical-align:middle;
			}
		}
	</style>

