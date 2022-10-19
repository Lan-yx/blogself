<template>
    
    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" :ellipsis="false" default-active="0"
        @select="handleSelect" background-color="#f4f4f4" text-color="#4a4a4a" active-text-color="#1b1b1b"
        style="--el-menu-hover-bg-color:#e7e7e7;" >
        <div class="lablefront">
            <a href="http://localhost:8080/" class="logolink">
                <button class="logobutton">
                    <span id="LOGO" index="0">LanYX</span>
                </button>
            </a>
        </div>
        
        <el-menu-item index="0" style="margin: 0 12px;">首页</el-menu-item>
        <el-menu-item index="1" style="margin: 0 12px;">时间轴</el-menu-item>
        <el-menu-item index="2" style="margin: 0 12px;">学习笔记</el-menu-item>
        <el-menu-item index="3" style="margin: 0 12px;">记录</el-menu-item>
        <el-menu-item index="4" style="margin: 0 12px;">工具</el-menu-item>
        
    </el-menu>
    
</template>
  
<script>
    export default{
        name: "Header"
    }
</script>
  
<style>
.el-menu{
    --el-menu-hover-bg-color:#000000;
}

.lablefront{
    width: calc(34% - 220px);
    display: flex;
    align-items: center;
    padding-left: 220px;
}
.logolink{
    height: 36px;
    min-width: 64px;
    padding: 0 16px;
    text-decoration: none;
    color: inherit!important;
    display: inline-block;
}
.logobutton{
    border: none;
    background-color: transparent;
    cursor: pointer;
    height: 100%;
}
#LOGO{
    font-size: 1.25rem!important;
    font-weight: 500;
    letter-spacing: .0125em!important;
}
</style>