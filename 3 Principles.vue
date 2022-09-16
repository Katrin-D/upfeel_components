<!-- upfeel.com/en -->
<!-- This component corresponds to the section with title
"OUR METHODOLOGY", green background on the middle of the page -->

<template>
  <section class="section principles" id="principles">
    <div class="container">
      <h2 class="principles-title">{{ $t("Section.Principles.title") }}</h2>
      <span> </span>
      <div class="principles-staticimg">
        <nuxt-picture
          class="principles-staticimg-ipad"
          src="principles/ipad.png"
          sizes="mobile:300px"
          :alt="$t('Section.Principles.alt.tablet')"
          :loading="loading"
        />
        <nuxt-picture
          class="principles-statistic-phone"
          src="principles/phone-2.png"
          sizes="mobile:150px"
          :alt="$t('Section.Principles.alt.smartphone')"
          :loading="loading"
        />
      </div>
      <nuxt-picture
        class="principles-ipad"
        src="principles/ipad.png"
        sizes="mobile:300px"
        :alt="$t('Section.Principles.alt.tablet')"
        :loading="loading"
      />
      <!-- v-rellax="rellaxIpad" data-rellax-percentage="0.5" -->
      <nuxt-picture
        class="principles-phone"
        src="principles/phone-2.png"
        sizes="mobile:150px"
        :alt="$t('Section.Principles.alt.smartphone')"
        :loading="loading"
      />
      <!-- v-rellax="rellaxPhone" data-rellax-percentage="0.5" -->
      <ul class="principles-list">
        <li v-for="principle in principles">
          <h3 class="principles-list-title">{{ principle.title }}</h3>
          <div class="principles-list-content">
            <p v-html="principle.content"></p>
          </div>
          <nuxt-img
            class="principles-list-separator"
            src="principles/separator.svg"
            alt="-"
            :loading="loading"
          />
        </li>
      </ul>
      <div class="principles-cta">
        <XyzTransition xyz="fade in" mode="in-out">
          <div class="principles-cta-quote">
            <p>{{ $t("Section.Principles.cta-quote") }}</p>
            <span class="principles-cta-quote-author">{{
              $t("Section.Principles.cta-quote-author")
            }}</span>
          </div>
        </XyzTransition>
        <b-button
          tag="nuxt-link"
          :to="localePath('/company-form')"
          type="is-primary"
          > {{ $t('Section.Principles.cta') }} </b-button
        >
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({ name: "SectionPrinciples" })
export default class SectionPrinciples extends Vue {
  @Prop()
  loading!:string

  rellaxIpad = { speed: 1 };
  rellaxLaptop = { speed: 4 };
  rellaxPhone = { speed: 3 };

  principles = [
    {
      title: this.$t("Section.Principles.item1-title"),
      content: this.$t("Section.Principles.item1-content"),
    },
    {
      title: this.$t("Section.Principles.item2-title"),
      content: this.$t("Section.Principles.item2-content"),
    },
    {
      title: this.$t("Section.Principles.item3-title"),
      content: this.$t("Section.Principles.item3-content"),
    },
    {
      title: this.$t("Section.Principles.item4-title"),
      content: this.$t("Section.Principles.item4-content"),
    },
    {
      title: this.$t("Section.Principles.item5-title"),
      content: this.$t("Section.Principles.item5-content"),
    },
  ];
}
</script>

<style lang="scss" scoped>
// Import the functions/mixins
@import "@animxyz/core";

@import "~/assets/style/variables";

.principles {
  position: relative;
  background: url("~assets/images/principles/bg-circles.svg") no-repeat top 100px center, $green;
  background-color: $green;
  background-size: initial;
  padding-top: 160px;
  @include from($desktop) {
    padding-top: 120px;
  }
  padding-bottom: 120px;
  color: $white;
  text-align: center;
  &::before {
    content: "";
    background: url("~assets/images/principles/brush-top-green.svg?data");
    top: -20px;
    left: 0;
    width: 100%;
    height: 39px;
    position: absolute;
  }
  .container {
    z-index: 1;
  }
  &-title {
    font-family: $family-heading;
    font-weight: normal;
    font-size: calc(2.5rem + 2vw);
    line-height: 1.1em;
    text-transform: uppercase;
    display: inline-block;
    position: relative;
    z-index: 8;
    margin-bottom: 0px;
    text-shadow: 0px 4px 3px rgba(0, 0, 0, 0.4), 0px 8px 13px rgba(0, 0, 0, 0.1),
      0px 18px 23px rgba(0, 0, 0, 0.1);
    @include from($tablet) {
      font-size: 3.5rem;
    }
    @include from($desktop) {
      text-shadow: none;
      margin-bottom: 50px;
    }
  }
  &-statistic {
    z-index: 1;
    position: relative;
    height: 300px;
    margin-top: -200px;
    margin-bottom: 0;
    @include from($desktop) {
      display: none;
    }
    &-ipad,
    &-laptop,
    &-phone {
      position: absolute;
      top: 0;
    }
    &-ipad {
      width: 300px;
      max-width: 80%;
      left: 0;
    }
    &-phone {
      width: 150px;
      max-width: 40%;
      top: 10%;
      right: 0;
    }
  }
  &-ipad,
  &-laptop,
  &-phone {
    position: absolute;
    top: 0;
    z-index: -1;
    display: none;
    @include from($desktop) {
      display: block;
    }
    // left: 50%;
  }
  &-ipad {
    width: 300px;
    top: 10%;
    // transform: translate(-320px, -100px);
    left: -100px;
    @include from($widescreen) {
      left: -50px;
    }
    @include from($fullhd) {
      left: 2%;
    }
  }
  &-laptop {
    width: 400px;
    // top:-100px;
    // transform: translate(-20px, -50px);
    top: 30%;
    right: -200px;
    @include from($widescreen) {
      right: -120px;
    }
    @include from($fullhd) {
      right: 0;
    }
  }
  &-phone {
    width: 150px;
    top: 50%;
    right: 0;
    @include from($widescreen) {
      right: 2%;
    }
    @include from($fullhd) {
      right: 6%;
    }
  }
  &-list {
    max-width: 550px;
    margin: auto;
    &-title {
      font-family: $family-heading;
      font-weight: normal;
      font-size: 2rem;
      line-height: 1.1em;
      margin-bottom: 20px;
    }
    &-content {
      margin-bottom: 30px;
    }
    &-separator {
      margin-bottom: 30px;
      filter: brightness(0) saturate(100%) invert(86%) sepia(5%) saturate(704%)
      hue-rotate(4deg) brightness(114%) contrast(85%);
    }
    li:last-child {
      .principles-list-separator {
        display: none;
      }
    }
  }
  .button {
    padding-left: 3em;
    padding-right: 3em;
    &::after {
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
