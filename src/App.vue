<script setup>
import ProjectHeader from './components/Header/ProjectHeader.vue'
import ProjectFooter from './components/Footer/ProjectFooter.vue'
</script>

<template>
  <ProjectHeader />
  <RouterView />
  <ProjectFooter />
</template>

<style lang="scss">
@use '@/assets/style/variables' as *;
@import '@/assets/fonts/stylesheet.css';

.router-link-reset {
  color: inherit;
  text-decoration: none;
}
.router-link-exact-active {
  color: #c4c4c4 !important;
}
.view {
  &__content-wrapper {
    margin-top: 2.75rem;
    margin-bottom: 13.75rem;
  }

  &__title {
    font-size: 2.5rem;
    font-weight: 800;
    margin-top: 1.5rem;
    margin-bottom: 0.75rem;
  }

  &__load-btn {
    text-transform: uppercase;
    font-size: 0.75rem;
    font-weight: 900;
    border: none;
    border-bottom: 2px solid black;
    border-radius: 0;
    padding-inline: 0;
    margin-top: 1.5rem;
    letter-spacing: 2px;
  }

  &__input {
    border-radius: 0;
    border: 1px solid #1e1e1e;
    padding: 1rem 2rem;

    &:hover::placeholder {
      transition: 0.5s;
      color: #c4c4c4;
    }
  }

  &__submit-btn {
    background: #1e1e1e;
    color: #ffffff;
    font-weight: 700;
    width: fit-content;
    border-radius: 0;
    padding: 1rem 5rem;
  }

  &__link-btn {
    display: flex;
    flex-flow: row;
    gap: 32px;
    align-items: center;
    border-radius: 0;
    color: #1e1e1e;
    background: #eeeeee;
    width: fit-content;
    font-weight: 800;
    font-size: 1rem;
    line-height: 175%;
    padding: 1.438rem 2rem;
  }

  &__date {
    text-transform: uppercase;
    font-size: 0.75rem;
    font-weight: 500;
    color: #c2c2c2;
  }

  &__card:hover &__card-title {
    color: $text-card-hover;
  }

  &__card-title {
    transition: $card-transition-duration;
    margin-top: 1.5rem;
    font-weight: 700;
    font-size: 24px;
  }
}

body {
  font-family: 'Gilroy';
}

.wrapper {
  max-width: calc(1150px + 2rem);
  width: 100%;
  padding-inline: 1rem;
  margin-inline: auto;

  &--default-m {
    margin-bottom: 13.75rem;
    margin-top: 2.75rem;
  }
}

/* .form-control {
  -webkit-appearance: button;
} */

.custom-select {
  position: relative;
}

.custom-select::before,
.custom-select::after {
  --size: 0.3rem;
  position: absolute;
  content: url('../../public/selectButton.svg');
  top: calc(50% - 11px);
  right: 3.5rem;
  pointer-events: none;
}

.form-control:focus {
  border-color: var(--bs-body-color);
  box-shadow: none;
}

.search-button {
  background: transparent url('../../public/searchIcon.svg') no-repeat center;
  width: 24px;
  cursor: pointer;

  &:hover {
    transition: 0.5s;
    background: transparent url('../../public/searchIconHover.svg') no-repeat center;
  }
}

@media screen and (max-width: 768px) {
  .search-button {
    background: transparent url('../../public/searchIconMobile.svg') no-repeat center;
  }
  .view {
    &__card-title {
      margin-top: 0.5rem;
      font-size: 1rem;
    }

    &__input {
      padding: 0.6875rem 1rem;
      &::placeholder {
        font-size: 0.5625rem;
      }
    }

    &__card-text {
      margin-top: 0.5rem;
      font-size: 0.75rem;
      margin-bottom: 2.5rem;
    }

    &__title {
      margin-top: 1rem;
      font-size: 1.25rem;
    }

    &__content-wrapper {
      margin-top: 1.5rem;
      margin-bottom: 5rem;
    }
  }
}
</style>
