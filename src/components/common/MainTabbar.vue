	<template>
		<tabbar>
      <tabbar-item path='/home'>
        <img src="~assets/img/tabbar/home.svg" slot='item-icon'>
        <img src="~assets/img/tabbar/home_active.svg" slot='item-active'>
        <div slot='item-text'>首页</div>
      </tabbar-item>
      <tabbar-item path='/class'>
        <img src="~assets/img/tabbar/class.svg" slot='item-icon'>
        <img src="~assets/img/tabbar/class_active.svg" slot='item-active'>
        <div slot='item-text'>分类</div>
      </tabbar-item>
      <tabbar-item path='/message'>
        <img src="~assets/img/tabbar/message.svg" slot='item-icon'>
        <img src="~assets/img/tabbar/message_active.svg" slot='item-active'>
        <div slot='item-text'>信息</div>
      </tabbar-item>
      <tabbar-item path='/profile'>
        <img src="~assets/img/tabbar/user.svg" slot='item-icon'>
        <img src="~assets/img/tabbar/user_active.svg" slot='item-active'>
        <div slot='item-text'>我的</div>
      </tabbar-item>
    </tabbar>
	</template>

	<script>
	  import Tabbar from 'common/tabbar/tabbar';
  	import TabbarItem from 'common/tabbar/tabbaritem/tabbaritem'
		export default{
		name:'MainTabbar',
		  components: {
		  	Tabbar,TabbarItem
		  },
			data(){
				return{

				}
			}

		}
	</script>

	<style scoped>

	</style>

