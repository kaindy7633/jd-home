<template>
  <div class="nearby">
    <h3 class="nearby__title">附近店铺</h3>
    <div
      v-for="item in nearbyList"
      :key="item.id"
      class="nearby__item"
    >
      <img class="nearby__item__img" :src="item.imgUrl" alt="">
      <div class="nearby__content">
        <div class="nearby__content__title">{{item.title}}</div>
        <div class="nearby__content__tags">
          <span
            v-for="(innerItem, innerIndex) in item.tags"
            :key="innerIndex"
            class="nearby__content__tag">
            {{innerItem}}
          </span>
        </div>
        <p class="nearby__content__highlight">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nearby',
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  setup () {
    const nearbyList = [
      {
        id: 1,
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        title: '沃尔玛',
        tags: ['月售1万+', '起送￥0', '基础运费￥5'],
        desc: 'VIP尊享满89元减4元运费运费券(每月5张)'
      },
      {
        id: 2,
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        title: '沃尔玛',
        tags: ['月售1万+', '起送￥0', '基础运费￥5'],
        desc: 'VIP尊享满89元减4元运费运费券(每月3张)'
      }
    ]
    return { nearbyList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/variables.scss';
.nearby {
  &__title {
    margin: .16rem 0 .02rem 0;
    font-size: .18rem;
    font-weight: normal;
    color: $content-fontcolor;
  }
  &__item {
    display: flex;
    padding-top: .12rem;
    &__img {
      width: .56rem;
      height: .56rem;
      margin-right: .16rem;
    }
  }
  &__content {
    flex: 1;
    border-bottom: 1px solid $content-bgcolor;
    padding-bottom: .12rem;
    &__title {
      line-height: .22rem;
      font-size: .16rem;
      color: $content-fontcolor;
    }
    &__tags {
      margin-top: .08rem;
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
    }
    &__tag {
      margin-right: .16rem;
    }
    &__highlight {
      margin: .08rem 0 0 0;
      line-height: .18rem;
      font-size: .13rem;
      color: #e93b3b;
    }
  }
}
</style>
