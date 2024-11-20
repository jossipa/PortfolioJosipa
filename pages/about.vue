<template>
  <div :style="{ backgroundColor: color }" class="page-container">
    <div class="demo-collapse container">
      <el-page-header :icon="ArrowLeft">
        <template #content>
          <span class="text-large font-600 mr-3">Title</span>
        </template>
      </el-page-header>
      <br>
      <br>
      <el-button plain @click="open">Molim?</el-button>
    </div>
    <br>
    <br>

    <el-color-picker v-model="color" show-alpha />
  </div>
</template>

<script lang="ts" setup>
import { ElMessage, ElMessageBox } from 'element-plus';
import type { Action } from 'element-plus';
import { ref } from 'vue';

// Reactive color state bound to el-color-picker
const color = ref('rgba(255, 255, 255, 0)');

const open = () => {
  ElMessageBox.alert('Opalim te golim', ';P', {
    confirmButtonText: 'Makse',
    callback: (action: Action) => {
      ElMessage({
        type: 'info',
        message: `action: ${action}`,
      });
    },
  });
};
</script>

<style scoped>
.page-container {
  margin: 40px;
  margin-top: 60px;
  min-height: 100vh; /* Ensure it covers the full viewport height */
  padding: 20px;
  transition: background-color 0.3s ease; /* Smooth transition */
}
</style>
