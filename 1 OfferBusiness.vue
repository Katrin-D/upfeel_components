<!-- upfeel.com/en -->
<!-- This component corresponds to the section with title
"Unique Collective Coaching Program fueled by humans and technology",
cream background and 5 round offers -->

<template>
  <section class="section offers" id="offer-business">
    <div class="container">
      <h2 class="section-title margin-auto" v-html="$t('Section.OfferBusiness.title')" />
      <p class="subtitle family-primary margin-auto" v-html="$t('Section.OfferBusiness.subtitle')" />
    </div>
    <div class="container">
      <div class="columns is-desktop">
        <nuxt-link
          v-for="card in cards"
          class="column is-one-third-desktop is-flex is-flex-direction-column"
          :to="localePath('/company-form')"
        >
          <div class="img-card">
            <figure class="image">
              <nuxt-img :src="card.picture" sizes="mobile:141px" loading="lazy" :alt="card.title"/>
            </figure>
          </div>
          <h3 class="section-title-small" v-html="card.title" />
          <p class="mb-5 offers-card-text" v-html="card.text" />
        </nuxt-link>
      </div>
      <div class="arrow-bottom">
        <div class="arrow-long">
          <img
            src="~/assets/images/offerBusiness/arrow-bottom-long.svg"
            alt="⟶"
            loading="lazy"
          />
          <p class="green section-title-small">{{ $t("Section.OfferBusiness.long-arrow") }}</p>
        </div>
        <div class="arrow-short">
          <img
            src="~/assets/images/offerBusiness/arrow-bottom-short.svg"
            alt="→"
            loading="lazy"
          />
          <p class="section-title-small">{{ $t("Section.OfferBusiness.short-arrow") }}</p>
        </div>
      </div>
      <b-button
        tag="nuxt-link"
        :to="localePath('/company-form')"
        type="is-primary"
        class="offer-button"
        > {{ $t('Section.OfferBusiness.cta1') }} </b-button
      >
    </div>
  </section>
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";
@Component({ name: "SectionOfferBusiness" })
export default class SectionOfferBusiness extends Vue {
  cards = [
    {
      picture: "offerBusiness/img-round-1.svg",
      title: this.$t("Section.OfferBusiness.title1"),
      text: this.$t("Section.OfferBusiness.text1"),
    },
    {
      picture: "offerBusiness/img-round-2.svg",
      title: this.$t("Section.OfferBusiness.title2"),
      text: this.$t("Section.OfferBusiness.text2"),
    },
    {
      picture: "offerBusiness/img-round-3.svg",
      title: this.$t("Section.OfferBusiness.title3"),
      text: this.$t("Section.OfferBusiness.text3"),
    },
    {
      picture: "offerBusiness/img-round-4.svg",
      title: this.$t("Section.OfferBusiness.title4"),
      text: this.$t("Section.OfferBusiness.text4"),
    },
    {
      picture: "offerBusiness/img-round-5.svg",
      title: this.$t("Section.OfferBusiness.title5"),
      text: this.$t("Section.OfferBusiness.text5"),
    },
  ];
}
</script>

<style lang="scss" scoped>
@import "~assets/style/variables";

.offers {
  padding-top: 100px;
  padding-bottom: 119px;
  position: relative;
  background: url("~assets/images/offerBusiness/one-circle-bg.svg") no-repeat
  bottom -10% left -15%, linear-gradient($cream, $cream);
  background-size: cover;
  text-align: center;
  width: 100%;

  .section-title {
    margin-bottom: 20px;

    &::before {
    content: url("~assets/images/hr-banner/hr-quote-brush.svg?data");
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
    z-index: -1;
  }
  }

  .section-title,
  .subtitle {
    position: relative;
    z-index: 5;
    @include from($desktop) {
      width: 70%;
    }
  }

  .columns {
    padding-top: 35px;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    @include from($desktop) {
      padding-top: 100px;
    }

    .column {
      margin: 0;
      padding: 1.8rem;
      flex: none;
      width: 100%;

      @include from(420px) {
        width: 80%;
      }
      @include from($tablet) {
        width: 35%;
      }
      @include until($desktop) {
        padding-bottom: 0;
      }
      @include from($desktop) {
        width: 20%;
      }

      &:first-child .arrow {
        display: none;
      }
    }
  }
  .img-card {
    position: relative;
    margin-bottom: 30px;
    z-index: 5;
    .image {
      border-radius: 0;
      width: 141px;
      margin: 0 auto;
      overflow: hidden;
      transition: ease all 0.5s;
    }
    .logo {
      position: absolute;
      top: 10%;
      right: 5%;
      z-index: 5;
      width: 28%;
      max-width: 150px;
    }
    .img-card-title {
      position: absolute;
      bottom: 0;
      left: 0;
      color: $white;
      font-size: calc(1.5rem + 1vw);
      padding: 1.5rem 2rem;
    }

    &:hover {
      .image {
        transform: scale(1.02);
      }
      &::after {
        transform: rotateZ(4deg);
      }
    }
  }
  .section-title-small {
    margin-bottom: 10px;
  }

  .button {
    margin-top: auto;
    transition: ease all 0.4s; // main
  }
  .arrow-bottom {
    display: none;
    @include from($desktop) {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      column-gap: 15px;
      margin-top: 10px;
      margin-right: -10px;
      margin-left: -10px;
      height: 80px;
      line-height: 0;
      .arrow-long {
        img {
          height: 35px;
        }
      }
      .arrow-short {
        img {
          height: 35px;
        }
      }
      .section-title-small {
        font-size: 26px;
      }
    }
  }
  .offer-button {
    padding-left: 3em;
    padding-right: 3em;
    margin-top: 60px;
    position: relative;
    transition: ease all 0.4s;
    @include until($desktop) {
      margin-top: 100px;
    }

    &::before {
      content: url("~assets/images/principles/circle.svg");
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      pointer-events: none;
    }
  }
  &::before {
    content: "";
    position: absolute;
    bottom: 100%;
    top: -25px;
    left: 0;
    z-index: 5;
    width: 100%;
    height: 30px;
    background: url("~assets/images/hr-banner/brush-top.svg?data") repeat-x
    center;
  }
}

</style>
