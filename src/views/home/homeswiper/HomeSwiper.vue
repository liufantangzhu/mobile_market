	<template>
		<swiper>
  		<swiper-item v-for='item in swiper'>
				<a :href="item.link">
					<img :src="item.href" alt="">
				</a>
  		</swiper-item>
  	</swiper>
	</template>

	<script>
		import {Swiper,SwiperItem} from 'common/swiper';

		export default{
		name:'HomeSwiper',
		props:{
			swiper:Array
		},
		  components: {
		  	Swiper,SwiperItem
		  },
			data(){
				return{

				}
			}

		}
	</script>

	<style scoped>

	</style>

