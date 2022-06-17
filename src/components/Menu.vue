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
      .col-wrap
        .col 
          .menu__bottom-col-title Мы в соц.сетях:
          ul.social
            li(v-for="social in socials")
              a(href="#" :class="social.modificatorClass") 
                i(:class="social.icon") 
        .col 
          .menu__bottom-col-title Телефон:
          ul
            li(v-for="phone in phones")   
              a(:href="`tel:${phone.phone}`") {{ phone.phone }}
        .col 
          .menu__bottom-col-title E-mail:
          ul
            li(v-for="email in emails") 
              a(href="mailto{{email.email}}") {{ email.email }} 
        .col 
          .menu__bottom-col-title Мессенжеры:
          ul.messengers
            li(v-for="messenger in messengers")
              a(href="#" :class="messenger.modificatorClass")
                i(:class="messenger.messengerClass") 
                span {{ messenger.messenger }}
                




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
    margin-bottom: 80px;

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

          &:hover {
            text-shadow: 4px 4px 4px rgba($mc, 0.5);
            -webkit-text-stroke: 1px $mc;
            color: transparent;
            font-weight: 300;
          }
        }
      }
    }
  }

  &__bottom {
    font-family: $jost;
    color: $wc;

    a {
      color: $wc;
      transition: $tr;

      &:hover {
        color: $mc;
      }
    }
  }

  &__bottom-col-title {
    color: $wc;
    font-weight: 600;
    line-height: 23px;
    margin-bottom: 15px;
  }

  &.open {
    animation-duration: 0.5s;
    animation-fill-mode: both;
    animation-name: bounce;
  }

  &.close {
    animation-duration: 0.5s;
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
          item: "Главная",
          link: "#",
        },
        {
          item: "Услуги",
          link: "#",
        },
        {
          item: "Портфолио",
          link: "#",
        },
        {
          item: "О компании",
          link: "#",
        },
        {
          item: "Блог",
          link: "#",
        },
        {
          item: "Магазин",
          link: "#",
        },
      ],
      subMenu: [
        {
          item: "разработка сайтов",
          link: "#",
        },
        {
          item: "iT-аутсорс",
          link: "#",
        },
        {
          item: "разработка дизайна",
          link: "#",
        },
        {
          item: "интернет маркетинг",
          link: "#",
        },
        {
          item: "консалтинг",
          link: "#",
        },
      ],
      socials: [
        {
          modificatorClass: "facebook",
          icon: "icon-facebook",
          link: "#",
        },
        {
          modificatorClass: "instagram",
          icon: "icon-instagram",
          link: "#",
        },
        {
          modificatorClass: "linkedin",
          icon: "icon-linkedin",
          link: "#",
        },
        {
          modificatorClass: "behance",
          icon: "icon-behance",
          link: "#",
        },
        {
          modificatorClass: "pinterest",
          icon: "icon-pinterest",
          link: "#",
        },
      ],
      phones: [
        {
          phone: "+996 505 225 777",
        },
      ],
      emails: [
        {
          email: "office@aizensoft.org",
        },
      ],
      messengers: [
        {
          messenger: "WhatsApp",
          messengerClass: "icon-whatsapp",
          modificatorClass: "whatsapp",
        },
        {
          messenger: "Telegram",
          messengerClass: "icon-paper-plane-empty",
          modificatorClass: "telegram",
        },
        {
          messenger: "Viber",
          messengerClass: "icon-viber",
          modificatorClass: "viber",
        },
      ],
    };
  },
};
</script>
