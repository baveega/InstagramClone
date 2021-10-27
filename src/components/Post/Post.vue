<template>
  <div class="post">
    <div class="post__upper">
      <img src="./../../assets/me.jpg" alt="owner" class="post__owner-img" draggable="false" />
      <a href="" class="post__owner align-middle">
        <span>Baveega</span>
      </a>

      <button class="post__options-menu" data-toggle="modal" data-target="#exampleModalCenter">
        <span class="dots">●●●</span>
      </button>
    </div>

    <div class="main-img">
      <img
        class="post__main-img"
        alt="main post"
        draggable="false"
        :src="post.mainImg"
        onDoubleClick="{this.handleLikePost}"
      />
    </div>

    <post-action></post-action>
    <div class="post__likes">1468 likes</div>
    <post-description :writer="post.creator" :description="post.description"></post-description>
    <post-comments :comments="comments"></post-comments>
  </div>
</template>

<script>
export default {
  name: 'Post',
  data: function() {
    return {};
  },
  methods: {},
  props: {
    post: {
      type: Object,
      required: true,
    },
    comments: {
      type: Array,
      required: true,
    },
  },
  components: {
    'post-action': () => import('./../PostAction/PostAction'),
    'post-description': () => import('./../PostDescription/PostDescription'),
    'post-comments': () => import('./../Comments/Comments'),
  },
};
</script>

<style lang="scss" scoped>
.post {
  background: white;
  margin-bottom: 60px;
  border: 2px solid lightgray;

  &__upper {
    padding: 10px 15px;
    border-bottom: 2px solid lightgray;
  }

  &__owner-img {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    border: 2px solid lightgray;
    background-color: white;
    padding: 1px;
  }

  &__owner {
    margin-left: 10px;
    color: rebeccapurple;
    font-size: 15px;
    font-weight: 600;
    letter-spacing: 2px;

    &:hover {
      text-decoration: none;
      color: rebeccapurple;
    }
  }

  &__options-menu {
    border: none;
    background: transparent;
    float: right;
    margin-top: 5px;

    &:focus {
      outline: 0;
    }
  }

  &__likes {
    padding-left: 1rem;
    font-weight: 600;
  }

  &__main-img {
    width: 100%;
    height: auto;
  }
}

.post-modal-choice {
  width: 100%;
  border: none;
  border-bottom: 2px solid lightgray;
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  background-color: transparent;
  font-size: 1rem;

  &:hover {
    outline: none;
  }

  &:active {
    outline: none;
  }
}

.modal-content {
  border-radius: 20px;
  width: 85%;
  margin: auto;
}

.danger-choice {
  color: red;
  font-weight: 700;
}

.lst-choice {
  border-bottom: none;
}

.dots {
  font-size: 10px;
  margin-top: 5px;
}
</style>
