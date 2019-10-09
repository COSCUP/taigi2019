<template>
  <div id="cfp" class="main-container">
    <Banner/>
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
