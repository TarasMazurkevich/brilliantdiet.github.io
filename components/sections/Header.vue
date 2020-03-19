<template>
  <header class="header">
    <div class="header_card">
      <header class="header_head">
        <div class="header-logo">
          <img src="/img/logo.svg" alt="Main logo this company">
        </div>
        <ul class="header_advantages">
          <li v-for="(advantage, i) in advantages" :key="i" class="header_advantage">
            <span class="header_advantage-icon"><i :class="advantage.icon" /></span>
            <p class="header_advantage-label">
              {{ advantage.text }}
            </p>
          </li>
        </ul>
      </header>
      <article class="header_article">
        <img src="/img/items/flower1.png" alt="" class="header_article-flower">
        <img src="/img/items/rings.svg" alt="" class="header_article-rings">
        <div class="header_top" data-class-desktop="left">
          <h1 class="header-title">
            Your instant weight-loss starts now
          </h1>
          <ul class="header_crumbs">
            <li v-for="(crumb, i) in crumbs" :key="i" class="header-crumb">
              {{ crumb }}
            </li>
          </ul>
          <ul class="header_governments">
            <p class="header_governments-title">
              This is Your best tool for:
            </p>
            <li v-for="(government, i) in governments" :key="i" class="header-government">
              <span>{{ government }}</span>
            </li>
          </ul>
        </div>
        <div class="header_bottom" data-class-desktop="right">
          <p class="header-p">
            «Be Brilliant» has already helped hundreds of Ladies on their way to smart healthy weight loss once and for all effortlessly
          </p>
          <p class="header-p">
            Becoming the «Be Brilliant» program member & be guided & coached by Professional Personal Trainer, Psychologist, Aesthetics Beautician, Nutrition Specialist.
          </p>
          <button class="header-btn">
            Chose program
          </button>
        </div>
      </article>
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      advantages: [
        { icon: 'fas fa-clock', text: 'Only 20 mins a day' },
        { icon: 'fas fa-weight', text: '- 2-7 kilos' },
        { icon: 'fas fa-money-bill-wave', text: 'From 3 dollars per day' }
      ],
      crumbs: ['Exclusive', 'Express', 'Easy'],
      governments: [
        'Instant sufficient weight-loss',
        'Inner beautification',
        'Self-esteem increase'
      ]
    }
  }
}
</script>

<style lang="scss">
  .header {
    width: 100vw;
    font-family: 'Ubuntu', sans-serif;

    @media only screen and (min-width: 991px) {
      height: 100vh;
      padding: 5em 10em;
      background-image: url('/img/bg/bg-header.jpg');
      background-position: cover;
      background-size: 100% 100%;
      background-repeat: no-repeat;
    }

    &_card {
      display: grid;
      grid-template-rows: auto 1fr;
      grid-row-gap: 1em;
      align-items: start;
      padding-bottom: 1em;
      width: 100%;
      height: 100%;
      background-image: url('/img/bg/bg-header-card.jpg');
      background-position: cover;
      background-size: 100% 100%;
      background-repeat: no-repeat;

      @media only screen and (min-width: 991px) {
        padding: 3em;
        padding-top: 2em;
        padding-right: 0;
      }
    }

    // HEADER -------------------------------

    &_head {
      display: grid;
      grid-template-columns: auto 1fr;
      grid-column-gap: 1em;
      align-items: center;
      justify-items: center;

      @media only screen and (min-width: 991px) {
        grid-column-gap: 5em;
        align-items: start;
      }
    }

    &-logo {
      width: 7em;
      height: 7em;
      box-shadow: 0 4px 15px 0 rgb(0,0,0);
      background-color: #0a2e24;

      @media only screen and (min-width: 991px) {
        width: 10em;
        height: 10em;
        transform: scale(1.5, 2) translate(20%, -20%);
      }

      img {
        width: 100%;
        height: 100%;
        @media only screen and (min-width: 991px) {
          width: 10em;
          height: 10em;
          transform: scaleY(.8);
        }
      }
    }

    &_advantages {
      @media only screen and (min-width: 991px) {
        justify-self: end;
        position: relative;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding-bottom: 2em;
        padding-right: 3em;
        width: 85%;
      }

      &::after {
        @media only screen and (min-width: 991px) {
          content: '';
          position: absolute;
          bottom: 0;
          left: 0;
          display: block;
          width: 100%;
          height: 3px;
          background-image: linear-gradient(165deg, #d5b174 0%, #fde5a5 50%, #c39d5f 100%);
        }
      }
    }

    &_advantage {
      display: grid;
      grid-template-columns: auto 1fr;
      align-items: start;
      justify-items: start;
      grid-column-gap: 10px;
      padding-right: 5px;

      @media only screen and (min-width: 991px) {
        font-weight: 700;
      }

      &:not(:first-child) {
        margin-top: 10px;

        @media only screen and (min-width: 991px) {
          margin-top: 0;
        }
      }
    }

    // ARTICLE -------------------------------

    &_article {
      $padding: 1em;

      position: relative;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      padding: {
        right: $padding;
        left: $padding;
      }
      overflow: hidden;

      @media only screen and (min-width: 991px) {
        display: grid;
        grid-template-columns: 3fr 2fr;
        margin-top: 3em;
        padding-right: 3em;
        overflow: visible;
      }

      &-flower {
        position: absolute;
        bottom: 0;
        left: 0;
        z-index: 1;
        transform: translate(-50%, 50%);

        @media only screen and (min-width: 991px) {
          transform: translate(-50%, 40%);
        }
      }

      &-rings {
        position: absolute;
        top: 40%;
        right: 0;
        z-index: 1;
        transform: translate(70%, -55%);

        @media only screen and (min-width: 991px) {
          transform: translate(50%, -25%);
        }
      }
    }

    &_top, &_bottom {
      z-index: 2;
    }

    &-title {
      font-size: 1.7em;
      font-weight: 700;
      color: #010101;

      @media only screen and (min-width: 991px) {
        font-size: 2em;
      }
    }

    &_crumbs {
      display: grid;
      grid-template-columns: repeat(3, auto);
      margin-top: 10px;

      @media only screen and (min-width: 991px) {
        display: flex;
      }
    }

    &-crumb {
      font-weight: 700;
      color: #010101;

      @media only screen and (min-width: 991px) {
        margin-top: 1em;
      }

      &:not(:first-child) {
        list-style-type: disc;
        list-style-position: inside;
        @media only screen and (min-width: 991px) {
          margin-left: 1em;
        }
      }
    }

    &_governments {
      display: flex;
      flex-direction: column;
      margin-top: 10px;

      @media only screen and (min-width: 991px) {
        margin-top: 2em;
      }
    }

    &-government {
      color: #d5b174;
      list-style-type: disc;
      list-style-position: inside;

      &:not(:first-child) {
        margin-top: 10px;
      }

      span {
        color: #010101;
      }
    }

    &-p {
      color: #010101;
      text-align: justify;
      margin-top: 10px;

      @media only screen and (min-width: 991px) {
        margin-top: 0;
        width: 80%;
      }

      &:not(:first-child) {
        @media only screen and (min-width: 991px) {
          margin-top: 2em;
        }
      }
    }

    &-btn {
      margin-top: 1em;
      padding: .5em 1em;
      background-color: #0a2e24;
      font-weight: 700;
      color: #f1bd7d;

      @media only screen and (min-width: 991px) {
        margin-top: 2em;
      }
    }
  }
</style>
