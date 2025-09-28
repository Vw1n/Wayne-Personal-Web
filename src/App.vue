<script setup>
import Header from './components/Header.vue';
</script>

<template>
  <div class="app">
    <Header />
    <main class="main-content">
      <section id="home" class="section">
        <div class="container">
          <h1>首页内容</h1>
          <p>欢迎访问我的个人网站！</p>
        </div>
      </section>
      <section id="about" class="section">
        <div class="container">
          <h2>关于我</h2>
          <p>这里是关于我的信息。</p>
        </div>
      </section>
      <section id="projects" class="section">
        <div class="container">
          <h2>项目</h2>
          <p>这里展示我的项目。</p>
        </div>
      </section>
      <section id="contact" class="section">
        <div class="container">
          <h2>联系方式</h2>
          <p>这里是我的联系方式。</p>
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex: 1;
}

.section {
  padding: 60px 0;
  border-bottom: 1px solid #eee;
}

.section:last-child {
  border-bottom: none;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* 确保页面内容不会被导航栏遮挡 */
.section {
  scroll-margin-top: 80px;
}
</style>
