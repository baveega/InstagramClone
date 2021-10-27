<template>
  <div class="home container">
    <div class="home__center">
      <home-stories></home-stories>
      <newsfeed></newsfeed>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data: function() {
    return {};
  },
  components: {
    newsfeed: () => import('./../components/Newsfeed/Newsfeed'),
    'home-stories': () => import('./../components/HomeStories/HomeStories'),
  },
};
</script>

<style lang="scss" scoped>
.home {
  &__center {
    width: 98.5%;
    margin-bottom: 30px;
  }


  @media (max-width: 768px) {
    &__center {
      width: 100%;
    }

  }
}
</style>
