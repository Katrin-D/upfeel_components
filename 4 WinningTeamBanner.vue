<!-- upfeel.com/en/products/collective-coaching -->
<!-- This component corresponds to the section with title
"One team, one operational goal, 4 months",
light-green background on the top of the page -->

<template>
  <section class="section winning-team-banner" id="winning-team-banner">
    <div class="container">
      <h2 class="winning-team-banner-title margin-auto" v-html="$t('Section.WinningTeamBanner.title')" />
      <ul class="winning-team-banner-list">
        <li v-for="item in items" class="">
          <div class="winning-team-banner-list-icon">
            <nuxt-img :src="item.picture" :alt="$t('Section.WinningTeamBanner.alt.picture')" :loading="loading"/>
          </div>
          <div>
            <h3 class="winning-team-banner-list-title" v-html="item.title" />
            <p class="winning-team-banner-list-text" v-html="item.text" />
          </div>
        </li>
      </ul>
      <b-button
        tag="a"
        href="#formbusiness"
        type="is-primary"
        class="winning-team-banner-button"
        >{{ $t('Section.WinningTeamBanner.button') }}</b-button
      >
    </div>
  </section>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({ name: "SectionWinningTeamBanner" })
export default class SectionWinningTeamBanner extends Vue {
  @Prop()
  loading!:string

  items = [
    {
      picture: "winning-team-banner/ico_1.svg",
      title: this.$t('Section.WinningTeamBanner.items.item1.title'),
      text: this.$t('Section.WinningTeamBanner.items.item1.text'),
    },
    {
      picture: "winning-team-banner/ico_2.svg",
      title: this.$t('Section.WinningTeamBanner.items.item2.title'),
      text: this.$t('Section.WinningTeamBanner.items.item2.text'),
    },
    {
      picture: "winning-team-banner/ico_3.svg",
      title: this.$t('Section.WinningTeamBanner.items.item3.title'),
      text: this.$t('Section.WinningTeamBanner.items.item3.text'),
    },
    {
      picture: "winning-team-banner/ico_4.svg",
      title: this.$t('Section.WinningTeamBanner.items.item4.title'),
      text: this.$t('Section.WinningTeamBanner.items.item4.text'),
    },
    {
      picture: "winning-team-banner/ico_5.svg",
      title: this.$t('Section.WinningTeamBanner.items.item5.title'),
      text: this.$t('Section.WinningTeamBanner.items.item5.text'),
    },
    {
      picture: "winning-team-banner/ico_6.svg",
      title: this.$t('Section.WinningTeamBanner.items.item6.title'),
      text: this.$t('Section.WinningTeamBanner.items.item6.text'),
    },
  ];
}
</script>

<style lang="scss" scoped>
@import "~assets/style/variables";
.winning-team-banner {
  padding-top: 54px;
  padding-bottom: 137px;
  color: $dark;
  position: relative;
  text-align: center;
  background-color: $green-light;
  background: url("~assets/images/winning-team-banner/bg-disc.svg?data")
      no-repeat top 192px left -6%,
    url("~assets/images/winning-team-banner/bg-circle.svg?data") no-repeat
      bottom 322px right -20%,
    $green-light;
  &::before {
    content: "";
    background: url("~assets/images/winning-team-banner/brush.svg?data");
    top: -27px;
    left: 0;
    width: 100%;
    height: 35px;
    position: absolute;
  }

  &-title {
    font-family: $family-heading;
    font-size: calc(2.5rem + 3vw);
    line-height: 68px;
    font-weight: normal;
    text-align: center;
    position: relative;
    margin-bottom: 131px;
    @include from($tablet) {
      font-size: 58px;
      max-width: 741px;
    }
    @include until(420px) {
      font-size: 47px;
    }

    &::after {
      content: url("~assets/images/winning-team-banner/brush-yellow.svg?data");
      position: absolute;
      top: 100%;
      left: 50%;
      transform: translateX(-50%);
      pointer-events: none;
    }
  }
  &-list {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;
    @include from($tablet) {
      & > :nth-child(2n) {
        align-self: flex-end;
      }
    }

    li {
      display: flex;
      align-items: flex-start;
      width: 100%;
      padding: 35px 0;
      @include from($tablet) {
        width: 70%;
      }
      @include from($desktop) {
        width: 50%;
        padding: 0 20px;
      }
    }

    &-icon {
      width: 90px;
      margin-right: 20px;
      flex-shrink: 0;
    }

    &-title {
      font-family: $family-secondary;
      font-size: 30px;
      font-weight: 700;
      line-height: 36px;
      letter-spacing: 0em;
      text-align: left;
      margin-bottom: 26px;
      @include until(420px){
        word-break: break-word;
      }
    }
    &-text {
      font-family: $family-primary;
      font-size: 16px;
      font-weight: 400;
      text-align: left;
    }
  }
  &-button {
    transition: ease all 0.4s;
    padding-left: 3em;
    padding-right: 3em;
    margin-top: 104px;
    position: relative;

    &::before {
      content: url("~assets/images/principles/circle.svg");
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }
  }
}
</style>
