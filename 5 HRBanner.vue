<!-- upfeel.com/en/products/collective-coaching -->
<!-- This component corresponds to the section with title
"WE ADDRESS YOUR OPERATIONAL CHALLENGES",
cream background on the middle of the page -->

<template>
  <section class="section hr-banner hr-banner-style2" id="hr-banner">
    <div class="container">
      <div class="columns">
        <div class="column hr-banner-picture">
          <nuxt-picture
            src="hr-banner/hr-picture.png"
            width="541"
            height="571"
            sizes="mobile:346px"
            :alt="$t('Section.HRBanner.alt.picture')"
            :loading="loading"
          />
        </div>
        <div class="column">
          <h2 class="hr-banner-title">
            {{ $t("Section.HRBanner.title") }}
          </h2>
          <p class="hr-banner-subtitle">
            {{ $t("Section.HRBanner.subtitle") }}
          </p>
        </div>
      </div>
      <ul class="columns is-multiline hr-banner-list">
        <li v-for="item in items" class="column is-half is-full-mobile">
          <div class="hr-banner-list-icon">
            <nuxt-img :src="item.picture" :alt="item.title" :loading="loading"/>
          </div>
          <div>
            <h3 class="hr-banner-list-title">{{item.title}}</h3>
            <p class="hr-banner-list-text" v-html="item.text" />
          </div>
        </li>
        <li class="column is-half is-full-mobile hr-banner-list-info">
          <p>{{ $t("Section.HRBanner.list-info") }}</p>
        </li>
      </ul>
      <div class="hr-banner-cta">
        <h3
          class="hr-banner-cta-title"
          v-html="$t('Section.HRBanner.cta-title')"
        />
        <b-button
          tag="nuxt-link"
          :to="localePath('/company-form')"
          type="is-primary is-medium"
          >{{ $t("Section.HRBanner.cta") }}</b-button
        >
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import {Vue, Component, Prop} from "nuxt-property-decorator";

@Component({ name: "SectionHRBanner" })
export default class SectionHRBanner extends Vue {
  @Prop()
  loading!:string

  items = [
    {
      picture: "hr-banner/ico_scaleup.svg",
      title: this.$t("Section.HRBanner.title1"),
      text: this.$t("Section.HRBanner.text1"),
    },
    {
      picture: "hr-banner/ico_luxe.svg",
      title: this.$t("Section.HRBanner.title2"),
      text: this.$t("Section.HRBanner.text2"),
    },
    {
      picture: "hr-banner/ico_conseil.svg",
      title: this.$t("Section.HRBanner.title3"),
      text: this.$t("Section.HRBanner.text3"),
    },
    {
      picture: "hr-banner/ico_car.svg",
      title: this.$t("Section.HRBanner.title4"),
      text: this.$t("Section.HRBanner.text4"),
    },
    {
      picture: "hr-banner/ico_tech.svg",
      title: this.$t("Section.HRBanner.title5"),
      text: this.$t("Section.HRBanner.text5"),
    },
    {
      picture: "hr-banner/ico_agence.svg",
      title: this.$t("Section.HRBanner.title6"),
      text: this.$t("Section.HRBanner.text6"),
    },
    {
      picture: "hr-banner/ico_ecom 1.svg",
      title: this.$t("Section.HRBanner.title7"),
      text: this.$t("Section.HRBanner.text7"),
    },
    {
      picture: "hr-banner/ico_parc.svg",
      title: this.$t("Section.HRBanner.title8"),
      text: this.$t("Section.HRBanner.text8"),
    },
  ];
}
</script>

<style lang="scss" scoped>
@import "~/assets/style/variables";

@keyframes rotating {
  from {
    -webkit-transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(360deg);
  }
}

.hr-banner {
  padding-top: 80px;
  padding-bottom: 220px;
  background: $cream;
  color: $dark;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    bottom: 100%;
    top: -6px;
    left: 0;
    width: 100%;
    height: 33px;
    background: url("~assets/images/hr-banner/brush-green.svg?data") repeat-x
    center;
  }
  .hr-banner-title {
    font-family: $family-heading;
    font-size: calc(2.5rem + 3vw);
    @include from($tablet) {
      font-size: 4.5rem;
    }
    line-height: 1em;
    font-weight: normal;
    margin-bottom: 20px;
  }
  .hr-banner-subtitle {
    font-size: 1.7rem;
    font-weight: normal;
    margin-bottom: 40px;
  }
  .hr-banner-picture {
    @include from($tablet) {
      order: 2;
    }
    max-width: 370px;
    position: relative;
    margin-top: -200px;
    picture {
      display: block;
      position: relative;
      &::before {
        content: "";
        position: absolute;
        width: 108%;
        height: 108%;
        top: -3%;
        left: -3%;
        background: url("~assets/images/hr-banner/circle.svg?data") center
          no-repeat;
        background-size: 100% 100%;
        z-index: 2;
        animation: rotating 15s linear infinite;
      }
    }
  }
  .hr-banner-list {
    li {
      display: flex;
      align-items: center;
      .hr-banner-list-icon {
        width: 90px;
        margin-right: 20px;
        flex-shrink: 0;
      }
    }
    &-title {
      font-family: $family-primary;
      font-size: 18px;
      font-weight: 700;
      text-align: left;
      margin-bottom: 8px;
    }
    &-text {
      font-family: $family-primary;
      font-size: 16px;
      font-weight: 400;
      text-align: left;
    }
    &-info {
      text-align: right;
      font-size: 0.8rem;
      line-height: 1.5em;
      color: $green;
      display: flex;
      justify-content: flex-end;
      @include from($tablet) {
        & > * {
          width: 80%;
        }
      }
    }
  }
  .hr-banner-cta {
    margin-top: 50px;
    text-align: center;
    position: relative;
    z-index: 5;
    &-title {
      font-size: 1.4rem;
      font-weight: normal;
      margin: 0 auto 40px auto;
      max-width: 800px;
      display: block;
    }
    &::before {
      content: url("~assets/images/hr-banner/hr-quote-brush.svg?data");
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translateX(-50%) translateY(-65%);
      z-index: -1;
      // opacity: .3;
    }
  }
  .button {
    transition: ease all 0.4s;
  }
}

.hr-banner-style2 {
  padding-bottom: 123px;
  background: url("~assets/images/offerBusiness/one-circle-bg.svg?data") no-repeat top -85% center,
  url("~assets/images/offerBusiness/big-circle-bg.svg?data") no-repeat bottom -12% right 15%, linear-gradient($cream, $cream);

  .hr-banner-title {
    margin-bottom: 40px;
    font-size: calc(2.5rem + 3vw);
    line-height: 68px;
    @include from($tablet) {
      font-size: 58px;
    }
  }

  .hr-banner-subtitle {
    font-family: $family-secondary;
    font-weight: 700;
    font-size: 1.375rem;
  }
  .hr-banner-list {
    li {
      align-items: flex-start;
    }
  }

  .hr-banner-cta,
  .hr-banner-list-info {
    display: none !important;
  }
}
</style>
