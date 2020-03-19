<template>
  <ul class="steps">
    <span class="steps-slide" @click="prevStep"><i class="fas fa-chevron-left" /></span>
    <li class="step">
      <span class="step-number">{{ CURRENT_STEP.number }}</span>
      <h4 class="step-title">
        {{ CURRENT_STEP.title }}
      </h4>
      <p class="step-desc">
        {{ CURRENT_STEP.desc }}
      </p>
    </li>
    <li v-for="(step, i) in steps" :key="i" class="step" data-class="dasktop">
      <span class="step-number">{{ step.number }}</span>
      <h4 class="step-title">
        {{ step.title }}
      </h4>
      <p class="step-desc">
        {{ step.desc }}
      </p>
    </li>
    <span class="steps-slide" @click="nextStep"><i class="fas fa-chevron-right" /></span>
  </ul>
</template>

<script>
export default {
  data () {
    return {
      currentStepIndex: 0,
      steps: [
        {
          number: '01',
          title: 'Chose EXCLUSIVE Program',
          desc: 'Get directions via e-mail after purchase join the group chat (available in P2 3) Anonymous - guaranteed.'
        },
        {
          number: '02',
          title: 'Follow EASY Instructions',
          desc: 'Delicious simple recipes 20 min effortless workouts you can do any time and any place Self-care daily routine for your face & body Coaching & motivation by best Professionals.'
        },
        {
          number: '03',
          title: 'Get EXPRESS Results',
          desc: 'Following the program instructions for only 2 weeks you will get - weight-loss up to 2-5 kg - Body shape reduce up to 3-10 cm in waist - Appetite control - Firm & glowing skin - In-love with yourself'
        }
      ]
    }
  },
  computed: {
    CURRENT_STEP () {
      return this.steps[this.currentStepIndex]
    }
  },
  methods: {
    nextStep () {
      if (this.currentStepIndex >= this.steps.length - 1) {
        this.currentStepIndex = 0
      } else {
        this.currentStepIndex++
      }
      console.log('ok')
    },
    prevStep () {
      if (this.currentStepIndex <= 0) {
        this.currentStepIndex = this.steps.length - 1
      } else {
        this.currentStepIndex--
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  $padding: 1em;
  .steps {
    display: grid;
    grid-template-columns: 1fr 9fr 1fr;
    align-items: center;
    grid-column-gap: 2em;
    margin-top: 1em;
    width: 100%;
    font-family: 'Ubuntu', sans-serif;
    text-align: center;
    z-index: 2;

    @media only screen and (min-width: 991px) {
      grid-template-columns: repeat(3, 1fr);
      justify-items: center;
      align-items: start;
      padding: 4em;
    }

    &-slide {
      color: #f1bd7d;

      @media only screen and (min-width: 991px) {
        display: none;
      }

      &:not(:first-child) {
        margin-top: 10px;
      }
    }
  }

  .step {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    font-weight: 700;
    color: #fff;

    @media only screen and (min-width: 991px) {
      display: none;
    }

    &[data-class="dasktop"] {
      display: none;

      @media only screen and (min-width: 991px) {
        display: grid;
        grid-template-columns: auto 1fr;
        grid-template-rows: auto 1fr;
        grid-template-areas: 'number title' 'desc desc';
        grid-column-gap: 1em;
        grid-row-gap: .7em;
        justify-items: start;
        align-items: start;
        text-align: left;
        width: 75%;
      }
    }

    &-number {
      grid-area: number;
      margin-top: .5em;
      font-size: 1.2em;
      color: #f1bd7d;

      @media only screen and (min-width: 991px) {
        color: #fff;
      }
    }
    &-title {
      grid-area: title;
      margin-top: .5em;
      font-size: 1.2em;
    }
    &-desc {
      grid-area: desc;
      margin-top: .5em;
      font-weight: 400;

      @media only screen and (min-width: 991px) {
        font-size: 14px;
      }
    }
  }
</style>
