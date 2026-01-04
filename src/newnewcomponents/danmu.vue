<template>
  <div class="danmu-container">
    <h3 class="title">vant 视频弹幕演示</h3>
    <!-- 弹幕容器 + 视频占位区 -->
    <van-barrage v-model="list" ref="barrage" :auto-play="false" rows="5">
      <div class="video">
        <div class="video-placeholder">视频区域</div>
      </div>
    </van-barrage>
    <!-- 控制按钮 -->
    <van-space class="control-group">
      <van-button @click="toggle" type="primary" size="small">
        {{ isPlay ? '暂停' : '开始' }}
      </van-button>
    </van-space>
  </div>
</template>
 

<script setup>
import { ref, watch } from 'vue';
import { Barrage as VanBarrage, Button as VanButton, Space as VanSpace } from 'vant';
import 'vant/lib/index.css';

const defaultList = [
  { id: 100, text: '弹幕16565' },
  { id: 101, text: '弹幕26565' },
  { id: 102, text: '弹幕35454' },
  { id: 103, text: '弹幕45454' },
  { id: 104, text: '弹幕54343' },
  { id: 105, text: '弹幕63232' },
  { id: 106, text: '弹幕7323232' },
];

const list = ref([...defaultList]);
const barrage = ref(null);
const isPlay = ref(false);
let timer = null;
let currentIndex = 0;

// 添加弹幕的方法
const add = () => {
  const item = defaultList[currentIndex % defaultList.length];
  list.value.push({
    id: Math.random(),
    text: item.text,
  });
}

// 按钮功能，播放/暂停
const toggle = () => {
  isPlay.value = !isPlay.value;
};

// 监听播放状态，实现能自动循环的效果
watch(isPlay, (val) => {
  if (val) {
    barrage.value?.play();
    timer = setInterval(() => {
      add();
    }, 1000);
  } else {
    barrage.value?.pause();
    clearInterval(timer);
    timer = null;
  }
});
</script>
<style scoped>
.danmu-container {
  padding: 10px;
  background: #fff;
  margin-bottom: 40px;
}

.title {
  margin-bottom: 15px;
  text-align: center;
  color: #323233;
  font-size: 18px;
  font-weight: 600;
}

.video {
  width: 100%;
  height: 150px;
  background-color: #222;
  position: relative;
  border-radius: 8px;
}

.video-placeholder {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #fff;
  font-size: 16px;
}

.control-group {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}
</style>
