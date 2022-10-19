<template>
    <div class="autoSwitch">
        <el-switch v-model="value1" size="large" active-text="自动播放"/>
        <!-- <el-switch v-model="value2" class="ml-2" style="--el-switch-on-color: #13ce66; --el-switch-off-color: #ff4949" /> -->
    </div>
    <el-carousel  trigger="click" arrow="never" interval="2000">
        <el-carousel-item>
            <img src="../assets/image/slide01.jpg" alt="">
            <!-- <h3 text="2xl" justify="center">{{ item }}</h3> -->
        </el-carousel-item>
        <el-carousel-item>
            <img src="../assets/image/slide02.jpg" alt="">
        </el-carousel-item>
        <el-carousel-item>
            <img src="../assets/image/slide03.jpg" alt="">
        </el-carousel-item>
        <el-carousel-item>
            <img src="../assets/image/slide04.jpg" alt="">
        </el-carousel-item>
        <el-carousel-item>
            <img src="../assets/image/slide05.jpg" alt="">
        </el-carousel-item>
        <el-carousel-item>
            <img src="../assets/image/slide06.jpg" alt="">
        </el-carousel-item>
    </el-carousel>
</template>
  
<script setup>

    import { ref } from 'vue'

    const value1 = ref(true)
    const value2 = ref(true)
</script>
    
<script>
    export default{
        name: "Slide"
    }
</script>

<style scoped>
.el-carousel {
    height: 80vh;
    min-height: 400px;
    border-radius: 8px;
    --el-carousel-indicator-width: 80px;
    --el-carousel-indicator-height: 3px;
}
.el-carousel__item{
    height: 80vh;
    min-height: 400px;
}
.el-carousel__item h3 {
    display: flex;
    color: #475669;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
}

.el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
    background-color: #d3dce6;
}

.autoSwitch{
    position: relative;
    left: 44%;
    margin: 10px 0;
}

</style>