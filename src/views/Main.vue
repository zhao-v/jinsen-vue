<template>
    <el-container style="height: 100%">
        <el-aside width="auto">
            <common-aside></common-aside>
        </el-aside>
        <el-container>
            <el-header>
                <common-header></common-header>
            </el-header>
            <el-main>
              <router-view></router-view>
            </el-main>
        </el-container>
    </el-container>
</template>

<script>
import CommonAside from "@/components/CommonAside";
import CommonHeader from "@/components/CommonHeader";

export default {
    name: "Main",
    components: {CommonHeader, CommonAside},
    data() {
        return {};
    },
};
</script>

<style lang="less" scoped>
.el-header {
    background-color: #333;
}

.el-aside {
    padding-top: 0;
}


</style>
