<template>
  <ul class="packages">
    <li v-for="(pack, i) in packs" :key="i" class="pack">
      <header class="pack_header">
        <h3 class="pack-title">
          Lose {{ pack.lose }} kg
        </h3>
        <p class="pack-name">
          {{ pack.name }}
        </p>
        <button class="pack-start">
          Start NOW
        </button>
      </header>
      <ul class="pack_services">
        <li v-for="(service, j) in pack.services" :key="j" class="pack-service">
          {{ service }}
        </li>
      </ul>
      <footer class="pack_footer">
        <p class="pack-price" :data-old="pack.oldPrice" :data-new="pack.newPrice">
          /
        </p>
        <p class="pack-format">
          {{ pack.format }}
        </p>
      </footer>
    </li>
  </ul>
</template>

<script>
export default {
  data () {
    return {
      packs: [
        {
          lose: '1-2',
          name: 'Centle smooth transformation',
          services: ['7 day menu', '7 work-out videos', 'Progress tracker'],
          oldPrice: '60 USD',
          newPrice: '39 USD',
          format: 'PDF file format'
        },
        {
          lose: '2-5',
          name: 'Effective Solution for Express weight-loss',
          services: [
            '14 day menu',
            '14 work-out videos',
            'Progress tracker',
            'Anticellulite body self message routine',
            'Daily affirmations for weight-loss',
            '24/7 group chat'
          ],
          oldPrice: '100 USD',
          newPrice: '49 USD',
          format: 'Materials distributed in Chat daily'
        },
        {
          lose: '3-7',
          name: 'Individual approach for impressive resuits',
          services: [
            '14 work-out videos',
            'Progress tracker',
            'Anticellulite body self message routine',
            'Daily affirmations for weight-loss',
            '24/7 group chat',
            'Additional Recipes after course (5 for each meal)',
            'Medical check-up list',
            'Beauty habits tracker'
          ],
          oldPrice: '100 USD',
          newPrice: '79 USD',
          format: 'Materials distributed in Chats daily. Individual meal plan to be sent individaully, designed on individual anamneses'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  $padding: 1em;
  .packages {
    display: grid;
    justify-items: center;
    align-items: start;
    margin-top: 1em;
    padding: $padding;
    width: 100%;
    font-family: 'Ubuntu', sans-serif;
    text-align: center;
    color: #fff;

    @media only screen and (min-width: 991px) {
      grid-template-columns: repeat(3, 1fr);
      grid-column-gap: 2em;
      margin-top: 0;
      padding: 0 7em;
      z-index: 2;
    }
  }

  .pack {
    display: grid;
    justify-items: center;
    align-items: start;
    width: 100%;
    background-image: url('/img/bg/bg-header-card.jpg');
    background-position: cover;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    box-shadow: 0 5px 30px -10px rgb(0,0,0);

    @media only screen and (min-width: 991px) {
      transform: translateY(-8em);
    }

    &:not(:first-child) {
      margin-top: 1em;

      @media only screen and (min-width: 991px) {
        margin-top: 0;
      }
    }

    &_header {
      position: relative;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: center;
      padding: .5em 1em;
      padding-bottom: 2em;
      width: 100%;
      background-image: linear-gradient(9deg, #cdad56 0%, #fdeda9 50%, #c7a74d 100%);
      color: #000;

      @media only screen and (min-width: 991px) {
        height: 8em;
      }
    }

    &-title {
      position: relative;
      font-size: 22px;
      font-weight: 700;

      &:after {
        content: '';
        position: absolute;
        bottom: -13px;
        left: 50%;
        display: inline-block;
        border-radius: 50%;
        width: 5px;
        height: 5px;
        background-color: #000;
        transform: translateX(-50%);
      }
    }

    &-name {
      margin-top: 1em;
      font-size: 18px;
      font-weight: 700;
    }

    &-start {
      position: absolute;
      bottom: 0;
      padding: .5em 1em;
      background-color: #0a2e24;
      font-weight: 700;
      color: #f1bd7d;
      transform: translateY(50%);
    }

    &_services {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-top: 1em;
      padding: 1em .5em;
      width: 100%;
      color: #000;
      font-size: 16px;
      font-weight: 400;

      @media only screen and (min-width: 991px) {
        height: 20em;
      }
    }

    &-service {
      position: relative;
      &:not(:first-child) {
        margin-top: 15px;
        &::before {
          content: '';
          position: absolute;
          top: -7px;
          left: 50%;
          width: 7px;
          height: 2px;
          background-color: #000;
          transform: translateX(-50%);
        }
      }
    }

    &_footer {
      position: relative;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding-top: 1em;
      padding-bottom: 1em;
      width: 100%;
      font-size: 16px;
      font-weight: 700;
      color: #000;

      @media only screen and (min-width: 991px) {
        height: 10em;
      }

      &::before {
        content: '';
        position: absolute;
        top: 0;
        left: 50%;
        width: 90%;
        height: 2px;
        background-color: #f1bd7d;
        opacity: .7;
        transform: translateX(-50%);
      }
    }

    &-price {
      font-size: 18px;
      font-weight: 700;
      color: #f1bd7d;

      &::before {
        content: attr(data-old);
        text-decoration: line-through;
      }
      &::after {
        content: attr(data-new);
        font-size: 28px;
        color: #000;
      }
    }

    &-format {
      margin-top: 10px;
      font-weight: 400;
    }
  }
</style>
