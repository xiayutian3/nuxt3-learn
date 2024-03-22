<template>
  <!-- 公共头部 -->
  <AppHeader/>
  
  <div class="wrapper">首页</div>
  <van-button type="primary">button</van-button>
  <VanButton type="success">button</VanButton>
</template>

<script setup lang="ts">
import type { VideoItem } from '@/types/video'
// 显示的列表
const list = ref<VideoItem[]>([])

// 动态设置seo
useSeoMeta({
  title: '我的神奇网站',
  ogTitle: '我的神奇网站',
  description: '这是我的神奇网站，让我来告诉你关于它的一切。',
  ogDescription: '这是我的神奇网站，让我来告诉你关于它的一切。',
  ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})

//发请求
const data = await useFetch('/api/channel', { method: 'GET'})

</script>
<style lang="scss">
.wrapper {
  color: lightgreen;
}
</style>