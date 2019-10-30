<template>
  <div id="banner" class="banner-container">
    <div class="banner-bg" ref="sightContainer">
      <Sight
        :width="sight.width"
        :height="sight.height"
        :spot="sight.spot"
      />
    </div>
    <header class="banner-header">
      <h3
        v-if="$route.name === 'CFP'"
        class="flag"
      >
        Call for Paper｜徵稿開催
      </h3>
      <h1 class="title bold">
        <span>COSCUP 2019 </span>
        <span v-html="parser('來/Lâi/台/Tâi/講/Káng/')"/>
      </h1>
      <h2
        class="subtitle"
        v-html="parser('來/Lâi/用/Iōng/台/Tâi/語/Gí/講/Kóng/開/Khai/源/Goân/')"
      />
      <p class="content">
        <span class="date">Dec. 21, 2019</span>
        <span class="place"><font-awesome-icon :icon="['fas', 'map-marker-alt']"/><a href="https://tools.wmflabs.org/geohack/geohack.php?params=24_9_8_N_120_41_0_E" target="_blank" rel="noopener noreferrer">　臺中科技大學</a></span>
      </p>
      <h2
        v-if="$route.name === 'CFP'"
        class="button"
      >
        <a href="https://docs.google.com/forms/d/e/1FAIpQLSfytjV4lqx06KUnLOdP0ejXV0mfrrfWRK68ESiHEUGSLZbGXw/viewform" target="_blank" rel="noopener noreferrer" v-html="parser('我/Góa/欲/Beh/投/Tâu/稿/Kó/')"></a>
      </h2>
    </header>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { Action, Getter } from 'vuex-class';

import { AppState } from '@/store/types/app';
import { pinYinParser } from '@/util/parser';
import Sight from '@/components/Sight.vue';

const namespace: string = 'app';

@Component({
  components: {
    Sight
  }
})
export default class Banner extends Vue {
  private parser = pinYinParser;

  @Action('setSight', { namespace }) private setSight: any;
  @Getter('sight', { namespace }) private sight: any;

  public mounted () {
    this.measureSightSize();

    window.addEventListener('resize', this.measureSightSize);
  }

  private measureSightSize () {
    const sightContainer: any = this.$refs.sightContainer;

    if (sightContainer.clientWidth > 840) {
      this.setSight({
        width: sightContainer.clientWidth,
        height: sightContainer.clientHeight,
        spot: {
          x: sightContainer.clientWidth / 2.0 + 140,
          y: sightContainer.clientHeight / 2.0 + 50
        }
      });
    } else {
      this.setSight({
        width: sightContainer.clientWidth,
        height: sightContainer.clientHeight,
        spot: {
          x: sightContainer.clientWidth + 50,
          y: sightContainer.clientHeight / 2.0 + 50
        }
      });
    }
  }
}
</script>
