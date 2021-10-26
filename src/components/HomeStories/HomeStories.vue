<template>
  <div class="home__stories">
    <div class="direc direc--left" @click="scroll_left">
      <img src="./../../assets/left-arrow.png" alt="left arrow" class="arrow" />
    </div>

    <div class="direc direc--right" @click="scroll_right">
      <img src="./../../assets/right-arrow.png" alt="right arrow" class="arrow" />
    </div>

    <div class="home__stories-wrapper">
      <div class="home__story" v-for="(story, index) in stories" :key="index">
        <div class="home__story-img">
          <img :src="story.img" :alt="story.name" class="story__img" />
        </div>

        <div class="home__story-owner">{{ story.name }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeStories',
  data: function() {
    return {
      stories: require('./../../mock/Profile/ProfileSuggestions').default,
    };
  },
  methods: {
    scroll_left() {
      let content = document.querySelector('.home__stories-wrapper');
      content.scrollLeft -= 75;
    },

    scroll_right() {
      let content = document.querySelector('.home__stories-wrapper');
      content.scrollLeft += 75;
    },
  },
};
</script>

<style lang="scss" scoped>
.home__stories {
  border: 2px solid lightgrey;
  background-color: white;
  margin-bottom: 24px;
  padding: 1em;;
  position: relative;

  .arrow {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    z-index: 1500;
    background-color: white;
  }

  .direc {
    top: 36%;
    position: absolute;
    cursor: pointer;
  }

  .direc--left {
    left: 1em;
  }

  .direc--right {
    right: 1em;
  }

  .home__stories-wrapper {
    display: flex;
    overflow-x: hidden;
    scroll-behavior: smooth;
  }

  .home__story {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
    justify-content: center;
    padding-right: 1em;;
    max-width: 80px;

    .home__story-img {
      margin-bottom: 7px;

      .story__img {
        width: 56px;
        height: 56px;
        border-radius: 50%;
        background-color: white;
        padding: 2px;
        border: 2px solid purple;
      }
    }

    .home__storyOwner- {
      color: darkgrey;
      font-size: 1.2em;;
    }
  }
}
</style>
