<template>
  <van-config-provider :theme="currentTheme">
    <AppLayout
      :onToggleTheme="toggleTheme"
      :currentTheme="currentTheme"
    />
  </van-config-provider>
</template>

<script setup>
import { ref } from "vue";
import AppLayout from "./components/AppLayout.vue";

const currentTheme = ref("light");

function toggleTheme() {
  currentTheme.value =
    currentTheme.value === "light" ? "dark" : "light";
}
</script>
