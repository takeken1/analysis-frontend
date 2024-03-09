<template>
    <div v-if="result">
      <h1>分析結果</h1>
      <p><strong>As-Is：</strong>{{ result.asIs }}</p>
      <p><strong>To-Be：</strong>{{ result.toBe }}</p>
      <!-- 他の結果も同様に表示 -->
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import type { PropType } from 'vue';
  
  export default defineComponent({
    name: 'AnalysisResult',
    props: {
      result: Object as PropType<{
        asIs: string;
        toBe: string;
        // 他のプロパティ定義
      }>,
    },
  });
  </script>
  
  <style scoped>
  /* ここにスタイルを追加 */
  </style>
  