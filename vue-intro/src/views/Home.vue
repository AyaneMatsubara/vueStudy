<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>すごいぞ！データバインディング<br>〜サンプル集〜</h1>

    <SampleFrame>
      <h2 slot="sample_title" class="sample_title">1.マスタッシュを使ってみよう</h2>
      <div slot="sample_cont" class="sample_cont">
        <p>文字を入力すると、それに合わせてテキストが変わります！</p>
        <input v-model="message">
        <p style="color: #41B883;">{{ message }}</p>
      </div>
    </SampleFrame>

    <SampleFrame>
      <h2 slot="sample_title" class="sample_title">2.v-forでリストを表示しよう</h2>
      <div slot="sample_cont" class="sample_cont">
        <p>v-forで繰り返し描画も簡単！もちろんデータと同期します</p>
        <ol class="sample_list">
          <li v-for="fruit in fruits">{{ fruit }}</li>
        </ol>
      </div>
    </SampleFrame>

    <SampleFrame>
      <h2 slot="sample_title" class="sample_title">3.イベント処理と条件分岐</h2>
      <div slot="sample_cont" class="sample_cont">
        <p>「クリックしたらテキストを変更」も数行で作れます</p>
        <nav class="sample_nav">
          <button v-on:click="changeArea('関東')">関東</button>
          <button v-on:click="changeArea('東海')">東海</button>
          <button v-on:click="changeArea('関西')">関西</button>
        </nav>
        <div v-if="area">
          <p>{{ area }}の式場一覧</p>
        </div>
        <div v-else>
          <p style="color: #a0a0a0; font-size: 16px;">エリアを選択してください</p>
        </div>
      </div>
    </SampleFrame>

  </div>
</template>

<script>
// @ is an alias to /src
import SampleFrame from '@/components/SampleFrame.vue'

export default {
  name: 'home',
  components: {
    SampleFrame
  },
  data() {
    return {
      message: 'Hello!',
      fruits: ["いちご🍓", "パイナップル🍍", "さくらんぼ🍒", "ピザ🍕"],
      area: ""
    }
  },
  methods: {
    changeArea(area) {
      this.area = area;
    }
  }
}
</script>

<style scoped>
  .sample_title {
    font-weight: normal;
  }

  .sample_cont {
    font-size: 20px;
  }

  .sample_list {
    text-align: left;
    width: 70%;
    margin: 0 auto 20px;
  }

  .sample_nav {
    display: flex;
    width: 60%;
    margin: 0 auto 20px;
  }

  .sample_nav button {
    background: #55BBC6;
    border: none;
    border-radius: 2px;
    padding: 4px 16px;
    color: #fff;
    cursor: pointer;
    width: 30%;
    margin: 0 3% 0;
  }
</style>
