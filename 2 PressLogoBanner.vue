<!-- upfeel.com/en -->
<!-- This component corresponds to the section with title
"They talk about us", white background and logos on the middle of the page -->

<template>
  <section class="section" id="press-logo-banner">
    <div class="container">
      <nuxt-link class="press-logo-banner" :to="localePath('/press')">
        <h2 class="press-logo-banner-title">{{ $t('Section.PressLogoBanner.title') }}</h2>
        <div class="logos">
          <div v-for="logo in logos" class="logo">
            <nuxt-picture :src="logo.picture" sizes="mobile:80px" height="40" fit="inside" alt="" :loading="loading"/>
          </div>
        </div>
      </nuxt-link>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component({ name: "SectionPressLogoBanner" })
export default class SectionPressLogoBanner extends Vue {
  @Prop()
  loading!:string

  logos=[
    { picture: 'press-logo-banner/europe1.png', alt: 'Europe1' },
    { picture: 'press-logo-banner/maddyness.png', alt: 'Maddyness' },
    { picture: 'press-logo-banner/figaro.png', alt: 'Le Figaro' },
    { picture: 'press-logo-banner/topsante.png', alt: 'Top Santé' },
    { picture: 'press-logo-banner/doctissimo.png', alt: 'Doctissimo' },
    { picture: 'press-logo-banner/depeche.png', alt: 'La Dépêche' },
    { picture: 'press-logo-banner/philomag.png', alt: 'Philosophie Magazine' },
    { picture: 'press-logo-banner/ladn.png', alt: "l'ADN" },
    { picture: 'press-logo-banner/echos.png', alt: 'Les Echos' },
    { picture: 'press-logo-banner/ccadres.png', alt: 'Courier Cadres' },
    { picture: 'press-logo-banner/bfm.png', alt: 'BTM TV' },
  ]
}
</script>

<style lang="scss" scoped>
@import "~/assets/style/variables";

.section {
  padding-top: 0;
  padding-bottom:0;
  position: relative;
  width: 100%;
  background-color: $white;
  @include until($tablet) {
    padding:0;
    .container {
      width:calc(100% + 40px);
      margin: 0 -20px;
      padding: 0;
    }
  }
  &::before {
    content: "";
    position: absolute;
    top: -25px;
    left: 0;
    width: 100%;
    height: 35px;
    background: url("~/assets/images/banner-logo/brush.svg") repeat-x center;
  }
}

.press-logo-banner  {
  display: block;
  position: static;
  top:0;
  padding: 60px 1.5rem;
  margin: 0 auto;
  width: 100%;
  text-align: center;
  @include from($desktop) {
    transform: translateY(-70%);
    width: 85%;
    max-width: 772px;
  }
  @include until($tablet) {
    width: 100%;
    max-width: 100%;
    position: relative;
    transform: none;
    margin-top: 0;
    margin-bottom: 0;
  }
  .container{
    z-index: 8;
  }
  &-title {
    font-family: $family-heading;
    font-size: 30px;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: 0em;
    text-align: center;
    margin-bottom: 40px;
  }
  .logos {
    display: flex;
    flex-wrap: wrap;
    row-gap: 20px;
    align-content: center;
    justify-content: space-between;
    margin: 0;
    .logo {
      width: 16%;
      padding: 5px;
      height: auto;
      line-height: 0;
      display: block;
      @include from($tablet) {
        width: 16%;
        padding: 10px;
      }
      picture {
        display: block;
        max-height: 45px ;
      }
    }
  }
}

</style>
