<template>
  <div v-if="result">
    <h1>分析結果</h1>
    <!-- choices 配列の最初の要素の message.content にバインド -->
    <p v-if="result.choices && result.choices.length > 0">
      <strong>アドバイス：</strong>{{ result.choices[0].message.content }}
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'AnalysisResult',
  props: {
    result: {
      type: Object,
      default: () => ({}),
    },
  },
});
</script>

<style scoped>
/* スタイル設定（変更不要） */
</style>
