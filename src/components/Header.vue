<template>
  <header class="header">
    <div class="container">
      <div class="logo">
        <a href="#">个人网站</a>
      </div>
      <nav class="nav">
        <ul class="nav-list">
          <li class="nav-item">
            <a href="#" class="nav-link">首页</a>
          </li>
          <li class="nav-item">
            <a href="#about" class="nav-link">关于我</a>
          </li>
          <li class="nav-item">
            <a href="#projects" class="nav-link">项目</a>
          </li>
          <li class="nav-item">
            <a href="#contact" class="nav-link">联系方式</a>
          </li>
        </ul>
      </nav>
      <div class="menu-toggle" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <!-- 移动端菜单 -->
    <div class="mobile-menu" v-show="isMobileMenuOpen">
      <ul class="mobile-nav-list">
        <li class="mobile-nav-item">
          <a href="#" class="mobile-nav-link" @click="toggleMenu">首页</a>
        </li>
        <li class="mobile-nav-item">
          <a href="#about" class="mobile-nav-link" @click="toggleMenu">关于我</a>
        </li>
        <li class="mobile-nav-item">
          <a href="#projects" class="mobile-nav-link" @click="toggleMenu">项目</a>
        </li>
        <li class="mobile-nav-item">
          <a href="#contact" class="mobile-nav-link" @click="toggleMenu">联系方式</a>
        </li>
      </ul>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';

// 控制移动端菜单的显示与隐藏
const isMobileMenuOpen = ref(false);

const toggleMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>

<style scoped>
/* 基础样式 */
.header {
  background-color: #ffffff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
}

.logo a {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  text-decoration: none;
}

/* 桌面端导航 */
.nav-list {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-item {
  margin-left: 30px;
}

.nav-link {
  text-decoration: none;
  color: #333;
  font-size: 16px;
  transition: color 0.3s;
}

.nav-link:hover {
  color: #007bff;
}

/* 移动端菜单按钮 */
.menu-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 21px;
  cursor: pointer;
}

.menu-toggle span {
  display: block;
  height: 3px;
  width: 100%;
  background-color: #333;
  border-radius: 3px;
}

/* 移动端菜单 */
.mobile-menu {
  position: absolute;
  top: 60px;
  left: 0;
  right: 0;
  background-color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.mobile-nav-list {
  list-style: none;
  margin: 0;
  padding: 0;
}

.mobile-nav-item {
  border-bottom: 1px solid #eee;
}

.mobile-nav-item:last-child {
  border-bottom: none;
}

.mobile-nav-link {
  display: block;
  padding: 15px 20px;
  text-decoration: none;
  color: #333;
  font-size: 16px;
}

.mobile-nav-link:hover {
  background-color: #f5f5f5;
  color: #007bff;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .nav {
    display: none;
  }
  
  .menu-toggle {
    display: flex;
  }
}
</style>