<template>
  <div id="app" class="app-container">
    <!-- 左上角进入后台按钮 -->
    <button class="admin-btn" @click="goToAdmin">进入后台</button>

    <!-- 主内容区域 -->
    <div class="content">
      <!-- 三个屏 -->
      <div
        v-for="(screen, index) in screens"
        :key="index"
        class="screen"
        :style="{ backgroundColor: screen.bgColor }"
      >
        <div class="screen-content">
          <p>{{ contentText }}</p>
        </div>
        <!-- 打分按钮 -->
        <div class="rating">
          <span v-for="star in 5" :key="star" class="star">
            <button @click="rateScreen(index, star)">
              {{ star }} ⭐
            </button>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contentText: "这里是一些可阅读的文字。",
      screens: [
        { bgColor: "#f8d7da" }, // 红色背景
        { bgColor: "#d4edda" }, // 绿色背景
        { bgColor: "#d1ecf1" }, // 蓝色背景
      
      ],
    };
  },
  methods: {
    goToAdmin() {
      alert("进入后台功能开发中...");
    },
    rateScreen(index, stars) {
      alert(`您为第 ${index + 1} 屏打了 ${stars} 星！`);
    },
  },
};
</script>

<style>
/* 全局样式 */
.app-container {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 0;
  padding: 0;
}

/* 左上角按钮 */
.admin-btn {
  position: absolute;
  top: 10px;
  left: 10px;
  padding: 8px 16px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
.admin-btn:hover {
  background-color: #0056b3;
}

/* 主内容区域 */
.content {
  display: flex;
  justify-content: center; /* 水平居中 */
  align-items: stretch;
  gap: 20px;
  margin-top: 20px;
  max-width: 1200px; /* 限制最大宽度 */
  margin-left: auto; /* 水平居中 */
  margin-right: auto; /* 水平居中 */
}

/* 单块屏 */
.screen {
  flex: 1;
  min-width: 0;
  display: flex;
  flex-direction: column;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* 屏内容 */
.screen-content {
  font-size: 16px;
  margin-bottom: 10px;
}

/* 打分按钮 */
.rating {
  display: flex;
  justify-content: space-around;
}
.star button {
  padding: 5px 10px;
  border: none;
  border-radius: 5px;
  background-color: #ffc107;
  cursor: pointer;
}
.star button:hover {
  background-color: #e0a800;
}
</style>
