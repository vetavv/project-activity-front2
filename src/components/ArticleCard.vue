<script setup>
defineProps({
  horizontal: Boolean
})
const title =
  'Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatu'
const text =
  'Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet,consectetur, adipisci velit, sed qu. Neque porro quisquam est, qui doloremipsum quia dolor sit amet, consectetur, adipisci velit, sed qu...'
const date = '22 сентября 2023'
const smallTitle = 'Excepteur sint occaecat cupidatat non proident'
</script>
<template>
  <div>
    <div
      class="d-flex article-card"
      :class="{ 'article-card--horizontal': horizontal, 'flex-column': !horizontal }"
    >
      <div class="article-card__scale-box">
        <img
          class="article-card__image"
          src="@/assets/images/article-example.png"
          :class="{ 'article-card__image--horizontal': horizontal }"
        />
      </div>

      <div class="article-card__text-content d-flex">
        <time class="article-card__date">{{ date }}</time>
        <router-link :to="{ name: 'article' }" class="router-link-reset">
          <span class="article-card__title" :class="{ 'article-card__title--small': horizontal }">
            {{ horizontal ? smallTitle : title }}
          </span>
        </router-link>
        <p class="article-card__text" v-if="!horizontal">{{ text }}</p>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.article-card {
  gap: 0.5rem;
  flex-direction: column;
  &:hover {
    .article-card__scale-box > img {
      transform: scale(1.15);
    }
    .article-card__title {
      color: #4c6eb9;
    }
  }
  &__scale-box {
    display: inline-block;
    overflow: hidden;

    position: relative;
    line-height: 0;
    & > img {
      transition: 1s;
      display: block;
    }
    &::after {
      content: '';
      display: block;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
      background: transparent;
      background-image: linear-gradient(to bottom, #1e1e1e00, #1e1e1ebe);
      opacity: 0.8;
    }
  }

  &__image {
    height: 22.5rem;
    width: 100%;
    object-fit: cover;
    /* max-width: 35rem; */
  }

  &__text {
    display: none;
  }
  &__text-content {
    font-weight: 700;
    font-size: 1.5rem;
    flex-direction: column-reverse;
  }
  &__date {
    text-transform: uppercase;
    font-size: 0.5rem;
    font-weight: 500;
    color: #c2c2c2;
  }
  &__title {
    display: inline-block;
    font-weight: 700;
    font-size: 0.75rem;
    margin: 0;
  }
}

@media (min-width: 768px) {
  .article-card {
    gap: 1.5rem;
    &--horizontal {
      flex-direction: row;
    }
    &__image {
      &--horizontal {
        max-width: 13rem;
        flex-basis: 40%;
        height: 8.75rem;
      }
    }
    &__title {
      &--small {
        font-size: 1rem;
      }
    }
    &__date {
      font-size: 0.75rem;
    }
    &__text {
      display: block;
      font-size: 1rem;
    }
    &__text-content {
      flex-shrink: 1;
      /* gap: 1.5rem; */
      flex-direction: column;
      font-weight: 400;
      font-size: 1rem;
    }
    &__title {
      display: inline-block;
      font-size: 1.5rem;
      margin: 1.5rem 0rem 0.5rem;
    }
  }
}
</style>
