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
	    <span>
          <a class="button" href="https://coscup2019.kktix.cc/events/coscup-taigi2019?utm_source=coscup&utm_medium=web&utm_campaign=taigi2019">報名</a>
	    </span>
      </p>
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

<style>
a.button {
  display: inline-block;
  padding: 1em 1.6em;
  color: white;
  background: #3b9c60;
  text-decoration: none;
}
</style>
