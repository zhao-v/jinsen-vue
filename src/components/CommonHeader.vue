<template>
  <div class="header">
    <div class="l-content">
      <el-button @click="headerMenu()" plain icon="el-icon-menu" size="mini"></el-button>
    </div>
    <div class="r-content">
      <el-dropdown trigger="click" size="mini">
        <span><img :src="userAvatar" alt="" class="user"></span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item @click.native="toHome">用户中心</el-dropdown-item>
          <el-dropdown-item @click.native="logout">退出登录</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonHeader",
  data() {
    return {
      userAvatar: require("@/assets/img/avatar.png")
    }
  },
  methods: {
    headerMenu() {
      this.$store.commit('collapseMenu');
    },
    logout() {
      localStorage.removeItem('user');
      this.$message.success("您已登出");
      this.$router.push({
        path: '/'
      });
    },
    toHome() {
          this.$router.push({
            name: 'home'
          })
    }
  }
}
</script>

<style lang="less" scoped>
.header {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: space-between;
  align-items: center;
}

.l-content {
  display: flex;
  align-items: center;

  .el-button {
    margin-right: 20px;
  }
}

.r-content {
  .user {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
}
</style>
