<template>
  <section class="programs">
    <header class="programs_head">
      <img src="/img/items/rings.svg" alt="" class="programs_head-rings">
      <img src="/img/items/glitter.png" alt="" class="programs_head-glitter">
      <h2 class="programs-title">
        Exclusive program for Express Weigh loss:
      </h2>
      <ul class="programs_advantages">
        <li v-for="(advantage, i) in advantages" :key="i" class="programs-advantage">
          <span>{{ advantage }}</span>
        </li>
        <button class="programs_advantages-btn">
          Join Be Brilliant
        </button>
      </ul>
    </header>

    <article class="programs_article">
      <div class="programs_top">
        <img src="/img/items/tape.png" alt="" class="programs_top-tape">
        <img src="/img/items/flower-colorful.png" alt="" class="programs_top-flower-colorful">
        <img src="/img/items/flower-not-complete.png" alt="" class="programs_top-flower-not-complete">
        <img src="/img/items/dark.png" alt="" class="programs_top-dark">
        <h3 class="programs_top-subtitle">
          How does it work?
        </h3>
        <ProgramSteps />
        <a href="#" class="programs_top-anchor">Start your Program NOW</a>
      </div>

      <div class="programs_bottom">
        <ProgramPacks />
      </div>
    </article>
  </section>
</template>

<script>

import ProgramSteps from '~/components/sliders/ProgramSteps'
import ProgramPacks from '~/components/sliders/ProgramPacks'

export default {
  components: {
    ProgramSteps,
    ProgramPacks
  },
  data () {
    return {
      advantages: [
        'Best professional coaches',
        'Only 2 weeks',
        'Delicious menu',
        'Daily easy 20 min workouts',
        'On-line motivation chat 24/7',
        'Anonymous guaranteed'
      ]
    }
  }
}
</script>

<style lang="scss">
  .programs {
    $padding: 1em;

    font-family: 'Ubuntu', sans-serif;

    // HEADER -------------------------------

    &_head {
      position: relative;
      display: grid;
      padding: {
        top: $padding;
        right: $padding;
        left: $padding;
      }
      overflow: hidden;

      @media only screen and (min-width: 991px) {
        grid-template-columns: repeat(2, 1fr);
        grid-column-gap: 4em;
        align-items: center;
        padding: 6em 10em;
      }

      &-rings {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        width: 300px;
        height: 300px;
        transform: translate(-30%, -30%);
        z-index: 1;

        @media only screen and (min-width: 991px) {
          width: 500px;
          height: 500px;
          transform: translate(20%, -5%);
        }
      }
      &-glitter {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;
        width: 150px;
        height: 150px;
        transform: translate(-30%, -10%);
        z-index: 1;

        @media only screen and (min-width: 991px) {
          width: 200px;
          height: 200px;
          transform: translate(60%, 70%);
        }
      }
    }

    &-title {
      font-size: 1.7em;
      font-weight: 700;
      color: #010101;
      z-index: 2;

      @media only screen and (min-width: 991px) {
        width: 70%;
        font-size: 2em;
      }
    }

    &_advantages {
      z-index: 2;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      margin-top: 3em;

      @media only screen and (min-width: 991px) {
        margin-top: 0;
      }
    }

    &-advantage {
      color: #d5b174;
      list-style-type: disc;
      list-style-position: inside;

      @media only screen and (min-width: 991px) {
        font-weight: 700;
      }

      &:not(:first-child) {
        margin-top: 5px;
      }

      span {
        color: #010101;
      }
    }

    &_advantages-btn {
      margin-top: 1em;
      padding: .5em 1em;
      background-color: #0a2e24;
      font-weight: 700;
      color: #f1bd7d;

      @media only screen and (min-width: 991px) {
        margin-top: 2em;
      }
    }

    // ARTICLE -------------------------------

    &_article {
      display: flex;
      flex-direction: column;
      margin-top: 1em;

      @media only screen and (min-width: 991px) {
        padding: 0 10em;
      }
    }

    &_top {
      position: relative;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: $padding;
      background-color: #0a2e24;
      overflow: hidden;

      @media only screen and (min-width: 991px) {
        padding-bottom: 15em;
      }

      // IMG ITEMS

      &-dark {
        position: absolute;
        top: 0;
        right: 0;
        z-index: 1;
        transform: translateY(-20%);
      }
      &-tape {
        position: absolute;
        top: 0;
        right: 0;
        z-index: 1;
        width: 150px;
        height: 150px;
        transform: translate(30%, -35%);
      }
      &-flower-not-complete {
        position: absolute;
        bottom: 0;
        right: 0;
        z-index: 1;
        width: 200px;
        height: 70px;
        transform: translate(33%, 0) rotate(90deg);
      }
      &-flower-colorful {
        position: absolute;
        bottom: 0;
        left: 0;
        z-index: 1;
        width: 250px;
        height: 250px;
        transform: translate(-50%, 50%);
      }

      // OTHER

      &-subtitle {
        font-size: 1.5em;
        font-weight: 700;
        color: #fff;
        text-align: center;

        @media only screen and (min-width: 991px) {
          margin-top: 1em;
          font-size: 2em;
        }
      }

      &-anchor {
        display: block;
        margin-top: 2em;
        text-align: center;
        color: #f1bd7d;
      }
    }

  }
</style>
