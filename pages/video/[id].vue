<template>
  <div>
    视频详情页 id
    {{ $route.params.id }}
  </div>
</template>

<script setup lang="ts">
// 页面路径  /video/xxxx

const { params } = useRoute()
console.log('params: ', params.id);

// 根据视频 id 获取视频详情
const { data: detail } = await useFetch(`/api/video/${params.id}`)


// SEO 优化
useSeoMeta({
  title: `${detail.value?.title} - 好了饿哦`,
})

</script>

<style scoped></style>