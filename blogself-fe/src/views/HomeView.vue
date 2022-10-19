<template>
  <el-scrollbar>
    <div class="container infinite-list-wrapper scrollbar-flex-content" style="overflow: auto">
      <div class="slider" style="max-width: 1080px; margin: auto; height: 80vh; padding: 0px 24px 40px;">
        <SlideWindow></SlideWindow>
      </div>
      <div class="body" style="max-width: 1080px;">
        <div class="content">
          <ul v-infinite-scroll="load" class="list" :infinite-scroll-disabled="disabled">
            <li v-for="i in count" :key="i" class="list-item">{{ i }}</li>
          </ul>
          <p v-if="loading">Loading...</p>
          <p v-if="noMore">&nbsp;&nbsp;&nbsp;&nbsp; No more</p>
        </div>
        <div class="aside">
          <ul class="tabs">
            <li class="tab">1111111111</li>
            <li class="tab">2222222222</li>
            <li class="tab">3333333333</li>
          </ul>
        </div>
      </div>
    </div>
  </el-scrollbar>

</template>

<script setup>
import { computed, ref } from 'vue'

const count = ref(10)
const loading = ref(false)
const noMore = computed(() => count.value >= 20)
const disabled = computed(() => loading.value || noMore.value)
const load = () => {
  loading.value = true
  setTimeout(() => {
    count.value += 2
    loading.value = false
  }, 2000)
}
</script>

<script>
import SlideWindow from '@/components/SlideWindow.vue'

export default {
  name: 'slide',
  components: {
    SlideWindow
  }
}
</script>

<style>

/* 整个滚动条 */
::-webkit-scrollbar {
    /* 对应纵向滚动条的宽度 */
    width: 8px;
    /* 对应横向滚动条的宽度 */
    height: 8px;
}

/* 滚动条上的滚动滑块 */
::-webkit-scrollbar-thumb {
    background-color: #dddedf;
    border-radius: 32px;
}

/* 滚动条轨道 */
::-webkit-scrollbar-track {
    background-color: #f4f4f4;
    border-radius: 32px;
}

.infinite-list-wrapper {
  background-color: #f4f4f4;
  text-align: center;

}

.infinite-list-wrapper .list {
  padding: 0;
  margin: 0;
  list-style: none;
}

.infinite-list-wrapper .list-item {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  background: var(--el-color-danger-light-9);
  color: var(--el-color-danger);
  border-radius: 8px;
  border: 1px solid #000;
}

.infinite-list-wrapper .list-item + .list-item {
  margin-top: 10px;
}

.body{
  margin-top: 30px;
  margin-left: auto;
  margin-right: auto;
}

.content{
  width: 60%;
  float: left;
  padding-left: 20px;
}

.aside{
  width: 30%;
  float: right;
  padding-right: 20px;
}

.aside .tabs{
  padding: 0;
  margin: 0;
  list-style: none;
}

.aside .tabs .tab{
  display: flex;
  margin-bottom: 10px;
  border-radius: 8px;
  align-items: center;
  justify-content: center;
  height: 100px;
  background: var(--el-color-success-light-9);
  color: var(--el-color-success);
  
  border: 1px solid #000;
}
</style>
