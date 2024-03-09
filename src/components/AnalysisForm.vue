<template>
    <div>
      <h1>問題分析フォーム</h1>
      <form @submit.prevent="submitForm">
        <div>
          <label for="userInput">問題点：</label>
          <textarea id="userInput" v-model="userInput" placeholder="あなたの問題をここに入力してください..."></textarea>
        </div>
        <button type="submit">分析開始</button>
      </form>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'AnalysisForm',
    setup() {
      const userInput = ref('');
  
      const submitForm = () => {
        console.log(userInput.value); // 本来はここでバックエンドAPIにリクエストを送る
        // 例: axios.post('/api/analyze', { input: userInput.value })
      };
  
      return {
        userInput,
        submitForm,
      };
    },
  });
  </script>
  
  <style scoped>
  /* ここにスタイルを追加 */
  </style>
  