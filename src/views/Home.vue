<template>
    <div>
        <el-container>
            <el-header>
                <el-row>
                    <el-col :span="4"><img src="@/assets/logo.png" alt=""></el-col>
                    <el-col class="middle" :span="19"><span>电商后台管理系统</span></el-col>
                    <el-col :span="1"><a class="logout" href="#">退出</a></el-col>
                </el-row>
            </el-header>
            <el-container>
                <el-aside width="200px">
                    <el-row class="tac">
                        <el-col>
                            <el-menu
                            :unique-opened="true"
                            :router="true"
                            style="height: 100%"
                            default-active="0">
                            <el-submenu index="1">
                                <template slot="title">
                                    <i class="el-icon-location"></i>
                                    <span>用户管理</span>
                                </template>
                                <el-menu-item-group>
                                    <el-menu-item index="1-1">
                                        <i class="el-icon-view"></i>
                                        用户列表
                                    </el-menu-item>
                                </el-menu-item-group>
                            </el-submenu>
                             <el-submenu index="2">
                                <template slot="title">
                                    <i class="el-icon-location"></i>
                                    <span>权限管理</span>
                                </template>
                                <el-menu-item-group>
                                    <el-menu-item index="2-1">
                                        <i class="el-icon-view"></i>
                                        角色列表
                                    </el-menu-item>
                                </el-menu-item-group>
                            </el-submenu>
                             <el-submenu index="3">
                                 <template slot="title">
                                    <i class="el-icon-location"></i>
                                    <span>商品管理</span>
                                </template>
                                <el-menu-item-group>
                                    <el-menu-item index="3-1">
                                        角色列表
                                    </el-menu-item>
                                    <el-menu-item index="3-2">
                                        分类参数
                                    </el-menu-item>
                                    <el-menu-item index="3-3">商品分类</el-menu-item>
                                </el-menu-item-group>
                            </el-submenu>
                             <el-submenu index="4">
                                 <template slot="title">
                                    <i class="el-icon-location"></i>
                                    <span>权限管理</span>
                                </template>
                                <el-menu-item-group>
                                    <el-menu-item index="4-1">
                                        <i class="el-icon-view"></i>
                                        角色列表
                                    </el-menu-item>
                                </el-menu-item-group>
                            </el-submenu>
                             <el-submenu index="5">
                                 <template slot="title">
                                    <i class="el-icon-location"></i>
                                    <span>权限管理</span>
                                </template>
                                <el-menu-item-group>
                                    <el-menu-item index="5-1">
                                        <i class="el-icon-view"></i>
                                        角色列表
                                    </el-menu-item>
                                </el-menu-item-group>
                            </el-submenu>
                            </el-menu>
                        </el-col>
                    </el-row>
                </el-aside>
                <el-main>
                </el-main>
            </el-container>
        </el-container>
    </div>
</template>

<script>
export default{
  beforeCreate() {
    const token = sessionStorage.getItem('token');
    if (!token) {
      this.$message.warning('请先登录');
      this.$router.push('/login');
    }
  }
};
</script>

<style>
  .logout {
    text-decoration: none;
    color: orange;
  }
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    /* text-align: center; */
    line-height: 60px;
  }
  .middle {
    text-align: center;
    line-height: 60px;
    font-size: 24px;
    color: #fff;
  }
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    /* text-align: center; */
    line-height: 200px;
   }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    /* text-align: center; */
    line-height: 160px;
  }

  body > .el-container {
    margin-bottom: 40px;
  }

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }

</style>
