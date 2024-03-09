<template>
    <div>
      <AnalysisForm @submit="handleSubmit" />
      <AnalysisResult v-if="analysisResult" :result="analysisResult" />
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import AnalysisForm from './AnalysisForm.vue';
  import AnalysisResult from './AnalysisResult.vue';
  
  export default defineComponent({
    name: 'MainContent',
    components: {
      AnalysisForm,
      AnalysisResult,
    },
    setup() {
      const analysisResult = ref(null);
  
      const handleSubmit = (userInput: string) => {
        // ここでバックエンドにリクエストを送り、結果を受け取る
        // 仮の結果を設定しています。実際にはAPIから受け取るデータに置き換えてください
        const result = {
          asIs: '現状の説明', // 仮のデータ
          toBe: '望ましい状態の説明', // 仮のデータ
          // 他の分析結果のデータもここに追加
        };
        analysisResult.value = result;
      };
  
      return {
        analysisResult,
        handleSubmit,
      };
    },
  });
  </script>
  