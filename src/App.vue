<template>
  <div id="app">
    
    <router-view/>

    <main-tabbar ></main-tabbar>
    
  </div>
</template>

<script>
  import MainTabbar from 'common/MainTabbar';
  export default {
    components: {
      MainTabbar 
    },
  mounted(){
    // this.scoll=new BScroll(document.querySelector('#app'),{probeType:3})
  }
  };
  
</script>

<style lang="scss">
@import "./assets/css/base.css";


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: rgba(255, 181, 206,1);
    }
  }
}
</style>
