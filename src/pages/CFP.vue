<template>
  <div id="cfp" class="main-container">
    <Banner/>
    <main class="spotlight-container">
      <div class="spotlight">
        <h1 class="font-black">贊助資訊</h1>
        <p>COSCUP 是由全志工籌辦舉辦的活動，活動也是開放大眾免費報名，我們誠摯地邀請台中在地或支持開源的企業組織成為本專場贊助商。</p>
        <p>歡迎來信洽詢 <a href="mailto:sponsorship@coscup.org" class="font-black">sponsorship@coscup.org</a></p>
      </div>
      <div class="spotlight">
        <h1 class="font-black">Code of Conduct</h1>
        <p class="paragraph">COSCUP 非常歡迎女性、跨性別與多元背景的投稿者。為了讓大家都能愉快的參加 COSCUP，我們鼓勵所有參與者閱讀年會的 <a href="https://hackmd.io/@coscup/cococo-zh" class="font-bold" target="_blank" rel="noopener noreferrer">行為守則（Code of Conduct）</a>，共同創造一個友善的環境。</p>
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Banner from '@/components/Banner.vue';

@Component({
  components: {
    Banner
  }
})
export default class CFP extends Vue {
  public mounted () {
    const title = document.querySelector('head>title');
    const metaList = Array.from(document.querySelectorAll('head>meta'));

    if (title) {
      title.innerHTML = 'COSCUP 2019 來台講 -- 世界頭一擺ê台語專場科技研討會';
    }

    metaList[3].setAttribute('content', 'COSCUP 2019 來台講 -- 世界頭一擺ê台語專場科技研討會');
    metaList[5].setAttribute('content', 'https://coscup.org/taigi2019/cfp');
    metaList[6].setAttribute('content', 'https://coscup.org/taigi2019/img/og.png');
  }
}
</script>
