<template>
  <van-nav-bar
    title="Title"
    :left-text="currentThemeIcon"
    right-text="refresh"
    @click-right="refresh"
    @click-left="onToggleTheme"
  />

  <van-tabbar v-model="active">
    <van-tabbar-item icon="home-o">Tab</van-tabbar-item>
    <van-tabbar-item icon="search">Tab</van-tabbar-item>
  </van-tabbar>
</template>

<script setup>
import { computed, ref } from "vue";

const props = defineProps([
  "onToggleTheme",
  "currentTheme",
]);

const currentThemeIcon = computed(() => {
  return props.currentTheme === "light" ? "🔆" : "🌙";
});

const active = ref(0);

function refresh() {
  window.location.reload();
}
</script>
