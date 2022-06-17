<template lang="pug">
<Menu :class="{ open: menuСondition, close: menuСlose }" />
header.header
  .container  
    .col-wrap
      .col
        .header__logo
          a(href="#")
            img(v-lazy="{ src: '/public/img/logo.png' }")
      .col
        .header__element
          .header__element-img
            img(v-lazy="{ src: '/public/img/header-element.png' }")
          .header__element-desc
            p(v-html="headerElementDesc")
      .col
        .hamburger(@click="hamburger" :class="{ open: menuСondition }")
           
</template>

<style lang="scss" scoped>
.header {
  padding: 27px 0;

  .col {
    width: 33.33%;

    &:nth-child(2) {
      @include jcc;
    }

    &:last-child {
      @include jfcfe;
    }
  }

  &__logo {
    max-width: 132px;
    width: 100%;
  }

  &__element {
    @include aistr;
  }

  &__element-img {
    max-width: 150px;
    width: 100%;
    @include aic;
  }

  &__element-img,
  &__element-desc {
    padding: 0 15px;
  }

  &__element-desc {
    border-left: 1px solid $wc;
    @include aic;

    p {
      font-weight: 300;
      color: $wc;
      font-family: $oswald;
      line-height: 23.71px;
    }
  }
}

.hamburger {
  position: relative;
  width: 40px;
  height: 30px;
  @include aic;
  cursor: pointer;

  &:hover {
    &:before,
    &:after {
      background-color: transparent;
      border: 1px solid $mc;
    }
    &:before {
      width: 32px;
    }

    &:after {
      width: 100%;
    }
  }

  &:before,
  &:after {
    position: absolute;
    content: "";
    height: 1px;
    background-color: $wc;
    transition: $tr;
    right: 0;
    border: 1px solid transparent;
  }

  &:before {
    width: 100%;
    margin-bottom: 8px;
  }

  &:after {
    width: 32px;
    margin-top: 8px;
  }

  &.open {
    &:before,
    &:after {
      width: 100%;
      margin: 0;
    }

    &:before {
      transform: rotate(45deg);
    }

    &:after {
      transform: rotate(-45deg);
    }
  }
}
</style>

<script>
import Menu from "@/components/Menu.vue";
export default {
  components: {
    Menu,
  },
  data() {
    return {
      headerElementDesc: "РАЗРАБОТКА САЙТОВ <br> В КЫРГЫЗСТАНЕ",
      menuСondition: false,
      menuСlose: false,
    };
  },
  methods: {
    hamburger() {
      this.menuСondition = !this.menuСondition;
      if (this.menuСondition == false) {
        this.menuСlose = true;
      } else {
        this.menuСlose = false;
      }
    },
  },
};
</script>
