<template>
  <section class="clients">
    <header class="clients_header">
      <h2 class="clients-title">
        Need to come up with some kind of heading
      </h2>
    </header>
    <article class="clients_article">
      <div class="clients_wrap">
        <div class="clients_shortInfo">
          <p class="clients-name">
            {{ CURRENT_CLIENT.name }}
          </p>
          <p class="clients-age">
            {{ CURRENT_CLIENT.age }} y.o
          </p>
          <p class="clients-weight">
            -{{ CURRENT_CLIENT.weightLos }} kg
          </p>
          <p class="clients-completed" /><h4>Program completed:</h4>{{ CURRENT_CLIENT.completed }}</p>
        </div>
        <div class="clients_imgBlock">
          <div class="clients_imgWrap">
            <img :src="CURRENT_CLIENT.before">
            <p class="clients-label">
              Before
            </p>
          </div>
          <div class="clients_imgWrap">
            <img :src="CURRENT_CLIENT.after">
            <p class="clients-label">
              After
            </p>
          </div>
        </div>
        <div class="clients_slideGroup">
          <button class="clients-slide" @click="prevSlide">
            <i class="fas fa-chevron-left" />
          </button>
          <button class="clients-slide" @click="nextSlide">
            <i class="fas fa-chevron-right" />
          </button>
        </div>
      </div>
      <div class="clients_desc">
        <ul class="clients_results">
          <h3 class="clients_results-title">
            Key results:
          </h3>
          <li v-for="(result, i) in CURRENT_CLIENT.keys" :key="i" class="clinets_result">
            {{ result }}
          </li>
        </ul>
        <p class="clients_feedback">
          <span>Anna's feedback</span>
          {{ CURRENT_CLIENT.feedback }}
        </p>
        <button class="clients-join">
          Join Be Brilliant
        </button>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  data () {
    return {
      clients: [
        {
          name: 'Diana',
          age: 35,
          weightLos: 9,
          completed: 'Delicate followed by Royal (5 weeks total)',
          before: '/img/clients/before1.jpg',
          after: '/img/clients/after1.png',
          keys: [
            '- learned how to build balanced delicious menu for herself and her family',
            '- learned how to lose weight even eating in restaurants',
            '- reduced cellulite',
            '- dropped from size XL to M'
          ],
          feedback: 'Amazing transformation of body and soul - I’m happy to be slender and to fit into designer clothes again! My husband could not believe that I can be so thin - I was never hungry and was eating lots of delicious meals during the program, and still saw my wight dropping fast daily. I want to thank «Be Brilliant» for the powerful support and gentle coaching. Definitely recommending you to everyone I know!'
        },
        {
          name: 'Lisa',
          age: 27,
          weightLos: 7,
          completed: 'Delicate followed by Royal (4 weeks total)',
          before: '/img/clients/before1.jpg',
          after: '/img/clients/after1.png',
          keys: [
            '- learned how to build balanced delicious menu for herself and her family',
            '- learned how to lose weight even eating in restaurants',
            '- reduced cellulite',
            '- dropped from size XL to M'
          ],
          feedback: 'Amazing transformation of body and soul - I’m happy to be slender and to fit into designer clothes again! My husband could not believe that I can be so thin - I was never hungry and was eating lots of delicious meals during the program, and still saw my wight dropping fast daily. I want to thank «Be Brilliant» for the powerful support and gentle coaching. Definitely recommending you to everyone I know!'
        },
        {
          name: 'Rose',
          age: 38,
          weightLos: 4,
          completed: 'Delicate followed by Royal (3 weeks total)',
          before: '/img/clients/before1.jpg',
          after: '/img/clients/after1.png',
          keys: [
            '- learned how to build balanced delicious menu for herself and her family',
            '- learned how to lose weight even eating in restaurants',
            '- reduced cellulite',
            '- dropped from size XL to M'
          ],
          feedback: 'Amazing transformation of body and soul - I’m happy to be slender and to fit into designer clothes again! My husband could not believe that I can be so thin - I was never hungry and was eating lots of delicious meals during the program, and still saw my wight dropping fast daily. I want to thank «Be Brilliant» for the powerful support and gentle coaching. Definitely recommending you to everyone I know!'
        }
      ],
      currentClientIndex: 0
    }
  },
  computed: {
    CURRENT_CLIENT () {
      return this.clients[this.currentClientIndex]
    }
  },
  methods: {
    nextSlide () {
      if (this.currentClientIndex >= this.clients.length - 1) {
        this.currentClientIndex = 0
      } else {
        this.currentClientIndex++
      }
    },
    prevSlide () {
      if (this.currentClientIndex <= 0) {
        this.currentClientIndex = this.clients.length - 1
      } else {
        this.currentClientIndex--
      }
    }
  }
}
</script>

<style lang="scss">
  $padding: 1em;

  .clients {
    font-family: 'Ubuntu', sans-serif;
    @media only screen and (min-width: 991px) {
      grid-template-columns: repeat(2, 1fr);
      grid-column-gap: 4em;
      align-items: center;
      padding: 6em 10em;
      padding-top: 0;
    }

    &_header {
      padding: {
        right: $padding;
        left: $padding;
      }

      @media only screen and (min-width: 991px) {
        padding: 0;
      }
    }

    &-title {
      font-size: 1.7em;
      font-weight: 700;

      @media only screen and (min-width: 991px) {
        width: 30%;
        font-size: 2em;
      }
    }

    // SHORT INFO FOR CLIENT

    &_article {
      @media only screen and (min-width: 991px) {
        display: grid;
        grid-template-columns: 2fr 1fr;
        margin-top: 2em;
      }
    }

    &_wrap {
      @media only screen and (min-width: 991px) {
        position: relative;
        display: grid;
        grid-template-columns: 2fr 1fr;
        grid-template-rows: repeat(2, 1fr);
        grid-template-areas: 'img desc' 'img slide';
        justify-items: start;
        align-items: center;
      }
    }

    &_shortInfo {
      display: flex;
      flex-direction: column;
      margin-top: 1em;
      padding: $padding;
      background-color: #0a2e24;
      font-size: 18px;
      color: #fff;

      @media only screen and (min-width: 991px) {
        grid-area: desc;
        margin-top: 0;
        box-shadow: 0 4px 15px 0 rgb(0,0,0);
        transform: translateX(-3em);
      }
    }

    &-name {
      font-weight: 700;
    }

    &-completed {
      margin-top: 1em;
      h4 {
        font-weight: 700;
      }
    }

    // IMG BLOCK

    &_imgBlock {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      justify-items: stretch;
      align-items: stretch;

      @media only screen and (min-width: 991px) {
        grid-area: img;
      }
    }

    &_imgWrap {
      width: 100%;
      height: 100%;
      object-fit: cover;

      img {
        width: 100%;
        height: 100%;
      }
    }

    &-label {
      position: relative;
      left: 50%;
      display: inline-block;
      padding: .2em;
      width: 90%;
      background-image: linear-gradient(9deg, #cdad56 0%, #fdeda9 50%, #c7a74d 100%);
      text-align: center;
      transform: translate(-50%, -50%);
    }

    // BTN FOR SLIDER

    &_slideGroup {
      position: absolute;
      right: 0;
      display: flex;
      margin-right: 5px;
      transform: translateY(-4em);

      @media only screen and (min-width: 991px) {
        position: static;
        grid-area: slide;
        justify-self: start;
        margin-right: 0;
        transform: translateY(0) translateX(-50%);
      }
    }

    &-slide {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 30px;
      height: 30px;

      @media only screen and (min-width: 991px) {
        width: 50px;
        height: 50px;
      }

      &:first-child {
        background-color: #fff;
        color: #000;
      }
      &:last-child {
        background-color: #0a2e24;
        color: #fff;
      }
    }

    // DESCRIPTION

    &_desc {
      margin-top: 1.5em;
      padding: {
        right: 1em;
        bottom: 1em;
        left: 1em;
      }

      @media only screen and (min-width: 991px) {
        margin-top: 0;
      }
    }

    &_results {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;

      &-title {
        font-size: 1.3em;
        font-weight: 700;

        @media only screen and (min-width: 991px) {
          padding-bottom: 1.5em;
        }
      }
    }

    &_feedback {
      margin-top: 1em;
      span {
        display: block;
        font-size: 1.3em;
        font-weight: 700;

        @media only screen and (min-width: 991px) {
          padding-bottom: 1.5em;
        }
      }
    }

    &-join {
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
