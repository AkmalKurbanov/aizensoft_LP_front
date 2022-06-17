<template lang="pug">
.hero
  .container
    .hero__top-line
      marquee(direction="right")
        .hero__item-title 
          span ЛЕНДИНГ
        .hero__item-title      
          span САЙТ ВИЗИТКА 
        .hero__item-title      
          span Интернет магазин
        .hero__item-title      
          span Индивидуальные проекты
        .hero__item-title      
          span Корполративные сайты
    .hero__left-line
      .hero__left-line-wrap
        marquee(direction="right")
          .hero__item-title 
            span ЛЕНДИНГ
          .hero__item-title      
            span САЙТ ВИЗИТКА 
          .hero__item-title      
            span Интернет магазин
          .hero__item-title      
            span Индивидуальные проекты
          .hero__item-title      
            span Корполративные сайты
</template>

<style lang="scss" scoped>
.hero {


  &__top-line {
    position: relative;

    &:before {
      position: absolute;
      content: '';
      width: 100%;
      height: 1px;
      background-color: $wc;
      left: 50%;
      transform: translateX(-50%);
    }

    marquee {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
    }
  }

  &__left-line {
    position: relative;
    width: 30px;
    height: 300px;
    margin-top: 30px;

    &:before {
      position: absolute;
      content: '';
      width: 1px;
      height: calc(100% - 10px);
      background-color: $wc;
      left: 50%;

    }
ао ооос  свьв алкакьлдцщ аоташлс сль сда ашкьажда
    .hero__left-line-wrap {
      transform-origin: left;
      position: absolute;
      width: 300px;
      height: 30px;
      bottom: -30px;
      left: 50%;
      transform: rotate(-90deg);
    }

  }

  &__item-title {
    width: 525px;
    display: inline-block;

    &:last-child {
      width: auto;
    }

    span {
      color: $wc;
      text-transform: uppercase;
      font-family: $over;
      font-size: 20px;
      background: $bc;
      padding: 0 15px;
    }
  }
}
</style>
<script></script>