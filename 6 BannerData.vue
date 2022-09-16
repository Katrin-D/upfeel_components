<!-- upfeel.com/en/products/collective-coaching -->
<!-- This component corresponds to the section with title
"A 100% measurable and ROI-oriented approach",
gray background and 2 graph -->

<template>
  <section class="section banner-data" id="banner-data">
    <div class="container">
      <h2 class="banner-data-title margin-auto" v-html="$t('Section.BannerData.title')" />
      <div class="columns is-tablet banner-data-cards">
        <nuxt-link
          v-for="card in cards"
          class="column banner-data-card is-one-third-tablet is-flex is-flex-direction-column"
          :to="localePath('/company-form')"
        >
          <figure class="banner-data-icon">
            <nuxt-img :src="card.picture" sizes="mobile:80px" :loading="loading" :alt="card.title"/>
          </figure>
          <h3 class="banner-data-icon-title" v-html="card.title" />
        </nuxt-link>
      </div>
      <div class="columns is-desktop banner-data-graphs">
        <div class="column banner-data-graph is-half-desktop">
          <nuxt-img
            src="~/assets/images/banner-data/line-graph.svg?data"
            width="363"
            height="271px"
            fit="cover"
            :loading="loading"
            alt="📈"
          />
        </div>
        <div class="column banner-data-graph is-half-desktop">
          <nuxt-img
            src="~/assets/images/banner-data/line-graph2.svg?data"
            width="322"
            height="271px"
            fit="cover"
            :loading="loading"
            alt="📈"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({ name: "SectionBannerData" })
export default class SectionBannerData extends Vue {
  @Prop()
  loading!:string

  cards = [
    {
      picture: "banner-data/icon_dashboard.svg",
      title: this.$t("Section.BannerData.title1"),
    },
    {
      picture: "banner-data/icon_profile.svg",
      title: this.$t("Section.BannerData.title2"),
    },
    {
      picture: "banner-data/icon_pulse.svg",
      title: this.$t("Section.BannerData.title3"),
    },
  ];
}
</script>

<style lang="scss" scoped>
@import "~assets/style/variables";

.banner-data {
  position: relative;
  background: url("~assets/images/principles/bg-grunge.jpg") no-repeat center;
  background-size: cover;
  padding-top: 50px;
  @include from($desktop) {
    padding-top: 63px;
  }
  padding-bottom: 63px;
  color: $white;
  text-align: center;
  &::before {
    content: "";
    background: url("~assets/images/banner-data/brush.svg?data");
    top: -15px;
    left: 0;
    width: 100%;
    height: 33px;
    position: absolute;
  }
  .container {
    width: 100%;
    margin: 0 auto;
    @include from($tablet) {
      max-width: 768px;
      font-size: 4.5rem;
    }
    @include from($desktop) {
      max-width: 1024px;
      font-size: 4.5rem;
    }
  }
  &-title {
    font-family: $family-heading;
    font-size: calc(2.5rem + 3vw);
    @include from($tablet) {
      font-size: 4.5rem;
      padding: 0 1em;
    }
    @include from($desktop) {
      font-size: 4.5rem;
      padding: 0 1.5em;
    }
    line-height: 1em;
    font-weight: normal;
    margin-bottom: 57px;
  }
  &-cards {
    position: relative;
    margin-bottom: 40px;
    @include from($tablet) {
      margin-bottom: 60px;
    }
    @include from($desktop) {
      margin-bottom: 100px;
    }
  }
  &-card {
    align-items: center;
    align-content: center;
    margin-bottom: 30px;
  }
  &-icon {
    width: 100px;
    height: 108px;

    &-title {
      width: 160px;
      margin-top: 20px;

      font-family: $family-heading;
      font-size: 30px;
      font-weight: 400;
      line-height: 40px;
      letter-spacing: 0em;
      text-align: center;
      color: $white;
      text-transform: uppercase;
    }
  }
  &-graphs::before {
    @include from($desktop) {
      content: url("~assets/images/banner-data/bg-brush.svg?data");
      position: absolute;
      width: 1200px;
      height: auto;
      filter: brightness(0) saturate(100%) invert(30%) sepia(12%) saturate(445%)
        hue-rotate(126deg) brightness(93%) contrast(84%);
      top: 80%;
      left: 50%;
      transform: translateX(-50%) translateY(-50%) rotate(-6deg);
    }
  }
  &-graph {
    position: relative;
    z-index: 2;
    @include until($desktop) {
      margin-bottom: 60px;
    }
  }
}
</style>
