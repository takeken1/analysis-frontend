<template>
    <div>
      <h1>問題分析フォーム</h1>
      <form @submit.prevent="submitForm">
        <div>
          <label for="userInput">問題点：</label>
          <textarea id="userInput" v-model="userInput" placeholder="あなたの問題をここに入力してください..." class="textarea"></textarea>
        </div>
        <button type="submit">分析開始</button>
      </form>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'AnalysisForm',
    setup(props, { emit }) {
      const userInput = ref('');
  
      const submitForm = () => {
        // 親コンポーネントにユーザー入力を送信
        emit('submit', userInput.value);
      };
  
      return {
        userInput,
        submitForm,
      };
    },
  });
  </script>
  
<style scoped>
.textarea {
  width: 100%; /* テキストエリアの横幅を100%に設定 */
  max-width: 100%; /* 最大横幅も100%に設定して、親要素を超えないようにする */
  min-height: 100px; /* テキストエリアの最小高さを設定 */
  padding: 8px; /* 内側の余白を設定 */
  box-sizing: border-box; /* padding と border を width と height に含める */
}
</style>
