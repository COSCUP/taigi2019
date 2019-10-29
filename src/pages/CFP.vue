<template>
  <div id="cfp" class="main-container">
    <Banner/>
    <main class="spotlight-container">
      <div class="spotlight">
        <h1 class="font-black">活動介紹</h1>
        <p>在台灣，不只開源文化需要推廣，台語文化也需要推廣與傳承，如果日常生活不常使用台語，我們也將失去以台語溝通解釋的能力。</p>
        <p>COSCUP 2019 來台講是一場「來用台語講開源」的專場活動，在過去 COSCUP 的研討會中，雖曾有幾位在地的社群朋友以台語進行 Open Source 技術演講，但大家還是普遍選擇以華文或英文為主，為此 COSCUP 將選在台北以外的地區，舉辦 COSCUP 2019 來台講，目的是希望讓大家有機會以台語進行技術交流，活絡台灣各地的開源社群聚會。</p>
      </div>
      <div class="spotlight">
        <h1 class="font-black">贊助資訊</h1>
        <p>COSCUP 是由全志工籌辦舉辦的活動，活動也是開放大眾免費報名，我們誠摯地邀請台中在地或支持開源的企業組織成為本專場贊助商。</p>
        <p>歡迎來信洽詢 <a href="mailto:sponsorship@coscup.org" class="font-black">sponsorship@coscup.org</a></p>
      </div>
      <div class="spotlight">
        <h1 class="font-black">Code of Conduct</h1>
        <p class="paragraph">SITCON 非常歡迎女性、跨性別與多元背景的投稿者。為了讓大家都能愉快的參加 SITCON，我們鼓勵所有參與者閱讀年會的 <a href="https://hackmd.io/@coscup/cococo-zh" class="font-bold" target="_blank" rel="noopener noreferrer">行為守則（Code of Conduct）</a>，共同創造一個友善的環境。</p>
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
      title.innerHTML = 'Call for Paper｜徵稿開催 — COSCUP 2019 來台講';
    }

    metaList[3].setAttribute('content', 'Call for Paper｜徵稿開催 — COSCUP 2019 來台講');
    metaList[5].setAttribute('content', 'https://coscup.org/taigi2019/cfp/');
    metaList[6].setAttribute('content', 'https://coscup.org/taigi2019/img/cfp-og.png');
  }
}
</script>
