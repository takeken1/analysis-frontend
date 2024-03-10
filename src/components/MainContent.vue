<template>
  <div>
    <AnalysisForm @submit="handleSubmit" />
    <AnalysisResult v-if="analysisResult" :result="analysisResult" />
  </div>
</template>

<script lang="ts">
import axios from 'axios';
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

    const handleSubmit = async (userInput: string) => {
      try {
        // POSTリクエストのボディを指定されたJSON形式に修正
        const response = await axios.post('http://127.0.0.1:8080/api/analysis/chat', {
          message: userInput,
        });
        analysisResult.value = response.data; // APIのレスポンスを直接結果にセット
      } catch (error) {
        console.error("APIからのデータ取得に失敗しました。", error);
        // エラーハンドリングをここで行う
      }
    };

    return {
      analysisResult,
      handleSubmit,
    };
  },
});
</script>
