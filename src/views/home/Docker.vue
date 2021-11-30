<template>
  <div class="docker">
    <div
      v-for="(item, index) in dockerList"
      :key="item.id"
      class="docker__item"
      :class="{'docker__item': true, 'docker__item--active': index===0}"
    >
      <div class="iconfont" v-html="item.icon" />
      <div class="docker__title">{{item.text}}</div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Docker',
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  setup () {
    const dockerList = [
      { id: 1, icon: '&#xe7c6;', text: '首页' },
      { id: 2, icon: '&#xe698;', text: '购物车' },
      { id: 3, icon: '&#xe713;', text: '订单' },
      { id: 4, icon: '&#xe78b;', text: '我的' }
    ]
    return { dockerList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/variables.scss';
.docker {
  display: flex;
  box-sizing: border-box;
  position: absolute;
  left: 0;
  bottom: 0;
  padding: 0 .18rem;
  width: 100%;
  height: 0.49rem;
  border-top: .01rem solid $content-bgcolor;
  color: $content-fontcolor;
  &__item {
    flex: 1;
    text-align: center;
    .iconfont {
      font-size: .18rem;
      margin: .07rem 0 .02rem 0
    }
    &--active {
      color: #1fa4fc;
    }
  }
  &__title {
    font-size: .2rem;
    transform: scale(.5, .5);
    transform-origin: center top;
  }
}
</style>
