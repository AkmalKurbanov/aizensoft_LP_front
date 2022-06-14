<template lang="pug">
.menu
  .menu__wrap.container
    .menu__top
      ul
        li(v-for="item in nav")
          a(href="#" @mouseenter="item = false") {{ item.item }}  
      ul
        li(v-for="item in subMenu")
          a(href="#") {{ item.item }}      
    .menu__bottom 


</template>

<style lang="scss">
.menu {
  position: fixed;
  width: 100%;
  height: 100%;
  background-color: $bc;
  transform: translateY(-100%);
  opacity: 0;

  &__wrap {
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 100%;
  }

  &__top {
    @include aifs-jfcsb;
    width: 100%;

    ul {
      padding: 0;

      &:last-child {
        text-align: right;
      }

      li {
        margin-bottom: 35px;

        &:last-child {
          margin-bottom: 0;
        }

        * {
          text-transform: uppercase;
          color: $wc;
          font-size: 54px;
          line-height: 54px;
          font-weight: 200;
          text-decoration: none;
          font-family: $jost;
          // -webkit-text-stroke: 1px $wc;
          // color: transparent;
        }
      }
    }
  }

  &.open {
    animation-duration: .5s;
    animation-fill-mode: both;
    animation-name: bounce;
  }

  &.close {
    animation-duration: .5s;
    animation-fill-mode: both;
    animation-name: close;
  }

  @keyframes bounce {
    0% {
      transform: translateY(-100%);
      opacity: 1;
    }

    50% {
      transform: translateY(100px) scaleY(0.8);
      opacity: 1;
    }

    100% {
      transform: translateY(0);
      opacity: 1;
    }
  }

  @keyframes close {
    0% {
      transform: translateY(0);
      opacity: 1;
    }

    100% {
      transform: translateY(-100%);
      opacity: 0;
    }
  }
}
</style>
<script>
export default {
  data() {
    return {
      nav: [
        {
          item: 'Главная',
          link: '#',
        },
        {
          item: 'Услуги',
          link: '#',
        },
        {
          item: 'Портфолио',
          link: '#',
        },
        {
          item: 'О компании',
          link: '#',
        },
        {
          item: 'Блог',
          link: '#',
        },
        {
          item: 'Магазин',
          link: '#',
        },
      ],
      subMenu: [
        {
          item: 'разработка сайтов',
          link: '#',
        },
        {
          item: 'iT-аутсорс',
          link: '#',
        },
        {
          item: 'разработка дизайна',
          link: '#',
        },
        {
          item: 'интернет маркетинг',
          link: '#',
        },
        {
          item: 'консалтинг',
          link: '#'
        },
      ]
    }
  }
}
</script>