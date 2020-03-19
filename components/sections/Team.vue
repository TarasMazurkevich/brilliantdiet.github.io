<template>
  <section class="team">
    <!-- <div class="documentsWrap">
      <ul class="documents">
        <li v-for="(doc, i) in ALL_DOCS" :key="i" class="documents_item">
          <div class="documents_imgWrap">
            <img :src="doc.Img" alt="Doc image" class="documents-img">
          </div>
          <div v-if="!IS_ACTION" class="documents_txtWrap">
            <p class="documents-txt">{{ doc.Name }}</p>
            <p class="documents-txt">{{ doc.Id }}</p>
            <p class="documents-txt">{{ doc.Date }}</p>
          </div>
          <div v-else class="documents_inputWrap">
            <input type="file" class="documents-input file" placeholder="Choose your photo" :id="'field' + i" v-model="doc.Img"/>
            <label :for="'field' + i">Choose image</label>
            <input type="text" class="documents-input" placeholder="Doc name" v-model="doc.Name" />
            <input type="text" class="documents-input" placeholder="Registration ID" v-model="doc.Id" />
            <input type="date" class="documents-input"  v-model="doc.Date"/>
          </div>
          <div class="documents_view">
            <i class="fas fa-eye"></i>
          </div>
        </li>
      </ul>
      <div @click="closePopup" class="popup" :class="{open: popupIsOpen}">
        <div class="popup_wrap">
          <img class="popup-img" :src="CURRENT_IMG">
        </div>
      </div>
    </div> -->

    <div class="team_card">
      <article class="owner">
        <div class="owner_imgWrap">
          <img src="/img/owner.jpg" alt="Owner avatar">
        </div>
        <ul class="owner_education">
          <h4>My education & degrees:</h4>
          <li v-for="(item, i) in educationList" :key="i">
            {{ item }}
          </li>
        </ul>
      </article>
      <article class="desc">
        <h2 class="desc-title">
          Who am I
        </h2>
        <p class="desc-subtitle">
          Good day, Dear!
        </p>
        <p class="desc-txt">
          It is my pleasure to provide you with an Express Weight-loss solution - «Be Brilliant» my best exclusive tool, which helps ladies all over the world to find an instant way to fit slim body, great health and unleashed Love to themselves
        </p>
        <p class="desc-txt">
          Having over 5 years practice as Nutrition Consultants and Wellness Coach, I realise the power the food can have on the mind and body & I am fulfilling my Mission daily - making people happier and healthier via the integration of Mindful Nutrition Therapy.
        </p>
        <p class="desc-txt">
          «Be Brilliant» is my best project, which has already helped hundreds of Ladies on their way to smart healthy weight loss once and for all effortless
        </p>
        <p class="desc-txt">
          I found the best specialists and formed the best team to design an exclusive working tool to reach your goal - slender toned body and strong health
        </p>
        <p class="desc-txt">
          By becoming the «Be Brilliant» program member, you will be guided & coached by Professional Personal Trainer, Psychologist, Aesthetics Beautician and me, as your Nutrition Specialist.
        </p>
        <p class="desc-txt">
          <strong>I’ve made weight-loss Express and Easy</strong>, and providing you an exclusive individual approach for impressive instant results!
        </p>
      </article>
      <ul class="coach_list">
        <h3 class="coach-title">
          Meet my team
        </h3>
        <li v-for="(coach, i) in coachList" :key="i" class="coach_item">
          <div class="coach_imgWrap">
            <img :src="coach.avatar">
          </div>
          <div class="coach_info">
            <p class="coach-name">
              {{ coach.name }}
            </p>
            <p class="coach-role">
              {{ coach.role }}
            </p>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      educationList: [
        'Stanford University «Introduction to Food and Health», «Child Nutrition and Cooking»',
        'Edinburgh University «Understanding Obesity»',
        'European Dietitian University «Modern Practical Dietology»',
        'National Research Tomsk State University «Molecular Dietology»'
      ],
      coachList: [
        { avatar: '/img/coach/coach1.jpg', name: 'Katheryn', role: 'Certified Personal Trainer' },
        { avatar: '/img/coach/coach1.jpg', name: 'Katheryn', role: 'Certified Personal Trainer' },
        { avatar: '/img/coach/coach1.jpg', name: 'Katheryn', role: 'Certified Personal Trainer' }
      ]
    }
  }
}
</script>

<style lang="scss">
  $padding: 1em;

  .team {
    margin-top: 1em;
    font-family: 'Ubuntu', sans-serif;

    @media only screen and (min-width: 991px) {
      width: 100vw;
      height: 110vh;
      padding: 5em 10em;
      background-image: url('/img/bg/bg-header.jpg');
      background-position: cover;
      background-size: 100% 100%;
      background-repeat: no-repeat;
    }

    &_card {
      @media only screen and (min-width: 991px) {
        display: grid;
        grid-template-columns: 2fr 4fr 1fr;
        grid-column-gap: 1em;
        justify-items: start;
        align-items: start;
        padding: 3em;
        padding-top: 2em;
        padding-right: 0;
        width: 100%;
        height: 100%;
        background-color: #fff;
      }
    }

    // OWNER

    .owner {
      display: grid;
      grid-template-columns: 4fr 2fr;

      @media only screen and (min-width: 991px) {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
        height: 100%;
        justify-items: start;
        align-items: start;
      }

      &_imgWrap {
        width: 100%;
        object-fit: cover;

        @media only screen and (min-width: 991px) {
          height: 100%;
          object-fit: contain;
        }

        img {
          width: 100%;
          height: 100%;

          @media only screen and (min-width: 991px) {
            height: auto;
          }
        }
      }

      &_education {
        align-self: center;
        display: flex;
        flex-direction: column;
        padding: 1em;
        width: 140%;
        background-color: #0a2e24;
        font-size: 13px;
        color: #fff;
        transform: translateX(-30%);

        @media only screen and (min-width: 991px) {
          width: 70%;
          transform: translate(0, -3em) scaleY(1.5);
        }

        h4 {
          font-size: 14px;
          font-weight: 700;
          padding-bottom: 1em;

          @media only screen and (min-width: 991px) {
            transform: scaleY(.5);
          }
        }

        li {
          list-style-type: disc;
          list-style-position: inside;

          @media only screen and (min-width: 991px) {
            transform: scaleY(.5);
          }
        }
      }
    }

    // DESCRIPTION

    .desc {
      margin-top: 1em;
      padding: {
        right: 1em;
        left: 1em;
      }

      &-title {
        font-size: 1.7em;
        font-weight: 700;
      }

      &-subtitle {
        margin-top: .5em;
        font-size: 1.3em;
        font-weight: 700;
      }

      &-txt {
        margin-top: .5em;
      }
    }

    // COACH
    .coach {
      &_list {
        display: flex;
        flex-direction: column;
        padding: 1em;

        @media only screen and (min-width: 991px) {
          display: grid;
          grid-template-columns: 1fr;
          grid-template-rows: auto repeat(3, 1fr);
          font-size: 1em;
        }

        h3 {
          font-size: 1.3em;
          font-weight: 700;

          @media only screen and (min-width: 991px) {
            font-size: 1em;
          }
        }
      }

      &_item {
        display: grid;
        grid-template-columns: 7em 1fr;
        grid-column-gap: .5em;
        margin-top: .5em;

        @media only screen and (min-width: 991px) {
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: flex-start;
          font-size: 13px;
        }
      }

      &_imgWrap {
        width: 100%;
        object-fit: cover;

        @media only screen and (min-width: 991px) {
            width: 7em;
        }

        img {
          width: 100%;
          height: 100%;
          padding {
            top: 50%;
            bottom: 50%;
          }

          @media only screen and (min-width: 991px) {
            padding: 0;
            height: auto;
          }
        }
      }
    }
  }
</style>
