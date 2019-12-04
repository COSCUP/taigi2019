<template>
  <div id="home" class="main-container">
    <Banner/>
    <main class="spotlight-container">
      <div class="spotlight">
        <h1 class="font-black">世界第一擺ê台語專場技術研討會，等你做夥來</h1>
        <p>咱全台灣有 80% ê人講台語，結果soah英語ê研討會比台語--ê較chē？你講你會曉講，按呢你kám想過beh按怎用台語解說電腦ê物仔？</p>
        <p>來來來，這著有一ê機會hōo--lí試看覓：COSCUP「來台講」，世界頭一擺ê台語專場技術研討會！</p>
      </div>
      <div class="spotlight">
        <h1 class="font-black">開源囡仔，做夥舞！</h1>
        <p>「台語開源研討會」hiah好耍（可能mā會足好聽）ê想法，咱這款ta̍k項攏愛家己舞ê開源人是當然愛做夥來插一kha，這má就來kā好料理款款--ê排上桌！</p>
        <ul class="bullets">
          <li>看 Wikidata 寫臺文ê 王文岳紹介台語ē多種姿態</li>
          <li>你咁有用 Line？ 林家煜有一tsiah完全用 kamigo 做出來ê muscle-man line bot</li>
          <li>Tēⁿ Hiàn Kun 做ê開源義手mā看會到，這枝手有目睭</li>
          <li>會曉念bē曉寫？吳家銘ê Chhōe台語來Phahkā你tàu-saⁿ-kāng</li>
          <li>著想要有台語文ê地圖？ 陳瑞霖講用 OpenStreetMap 做台語、客家話ê地圖嘛會使</li>
          <li>手機仔唔夠 open？kā freedom 做夥用 open-source 工具來探看走 iOS ê物仔內底kah溫度相關ê軟體kah硬體</li>
          <li>電腦要怎樣講台語？意傳科技來紹介全全開源ê語音合成──媠聲SuíSiann</li>
        </ul>
        <p>不管你是台語輾轉到會當主持婚宴ê老司機，抑是勉強聽有m̄-koh一句講都bē曉話ê菜鳥仔，攏歡迎來參加這場有夠純koh豐沛ê台語盛會，看咱ê Taiwanese 和 Open Source kap-kap做夥會當變出啥物báng！</p>
      </div>
      <div class="spotlight">
        <h1 class="font-black">活動資訊</h1>
        <ul class="bullets">
          <li>時間：2019/12/21（六） 09:30 - 17:00</li>
            <li>地點：國立臺中科技大學 中技大樓 2F 多媒體會議室<br>（404 台中市北區錦平街 40 號，<a href="https://www.nutc.edu.tw/files/11-1000-150.php">交通資訊</a>、<a href="https://tools.wmflabs.org/geohack/geohack.php?params=24_9_8_N_120_41_1_E">地點座標 / GeoLocation</a>）</li>
          <li>報名時間：2019/12/04 12:00 (+0800)</li>
        </ul>
      </div>
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
export default class Home extends Vue {
  public mounted () {
    const title = document.querySelector('head>title');
    const metaList = Array.from(document.querySelectorAll('head>meta'));

    if (title) {
      title.innerHTML = 'COSCUP 2019 來台講';
    }

    metaList[3].setAttribute('content', 'COSCUP 2019 來台講');
    metaList[5].setAttribute('content', 'https://coscup.org/taigi2019/cfp/');
    metaList[6].setAttribute('content', 'https://coscup.org/taigi2019/img/og.png');
  }
}
</script>

<style>
ul.bullets {
  list-style: disc;
  padding-left: 1.6em;
}
ul.bullets > li {
  line-height: 1.6em;
}
</style>
