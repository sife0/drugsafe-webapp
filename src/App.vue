<template>
  <el-container>
<!--    <el-container>-->
<!--      <el-aside>-->
<!--        <el-menu-->
<!--          background-color="#545c64"-->
<!--          text-color="#fff"-->
<!--          active-text-color="#ffd04b"-->
<!--          :default-active="activeIndex"-->
<!--          router-->
<!--          style="min-height:100vh;float:left;width: 90%;text-align: center;"-->
<!--        >-->
<!--          <NavMenu :navMenus="menuData"></NavMenu>-->
<!--        </el-menu>-->
<!--      </el-aside>-->
<!--      <el-container>-->
<!--        <el-main>-->
<!--          <router-view></router-view>-->
<!--        </el-main>-->
<!--      </el-container>-->
<!--    </el-container>-->
    <router-view></router-view>
  </el-container>
</template>

<script>
import NavMenu from "./components/NavMenu.vue";
export default {
  components: {
    NavMenu: NavMenu
  },
  data() {
    return {
      activeIndex: 'pharmacy',
      menuData: [
        {
          //一级
          entity: {
            id: 0,
            name: "pharmacy",
            alias: "药店管理"
          }
        },
      ],
    };
  },
  mounted(){
    console.log(window.location.href)
    let start = window.location.href.lastIndexOf('/');
    let path = window.location.href.slice(start+1);
    this.activeIndex = path;

    console.log(this.activeIndex)
  }

};
</script>

<style>
</style>
