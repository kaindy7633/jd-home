<template>
  <div class="position">
    <span class="iconfont position__icon">&#xe7f1;</span>
    北京理工大学国防科技园2号楼10层
    <span class="iconfont position__notice">&#xe60d;</span>
  </div>
  <div class="search">
    <span class="iconfont">&#xe6e1;</span>
    <span class="search__text">山姆会员商店优惠商品</span>
  </div>
  <div class="banner">
    <img class="banner__img" src="http://www.dell-lee.com/imgs/vue3/banner.jpg" alt="">
  </div>
  <div class="icons">
    <div
      v-for="item in iconsList"
      :key="item.id"
      class="icons__item"
    >
      <img class="icons__item__img" :src="`http://www.dell-lee.com/imgs/vue3/${item.imgName}.png`" alt="">
      <p class="icons__item__desc">{{item.desc}}</p>
    </div>
  </div>
  <div class="gap"></div>
</template>

<script>
export default {
  name: 'StaticPart',
  // eslint-disable-next-line @typescript-eslint/explicit-module-boundary-types
  setup () {
    const iconsList = [
      { id: 1, imgName: '超市', desc: '超市便利' },
      { id: 2, imgName: '菜市场', desc: '菜市场' },
      { id: 3, imgName: '水果店', desc: '水果店' },
      { id: 4, imgName: '鲜花', desc: '鲜花绿植' },
      { id: 5, imgName: '医药健康', desc: '医药健康' },
      { id: 6, imgName: '家居', desc: '家居时尚' },
      { id: 7, imgName: '蛋糕', desc: '烘焙蛋糕' },
      { id: 8, imgName: '签到', desc: '签到' },
      { id: 9, imgName: '大牌免运', desc: '大牌免运' },
      { id: 10, imgName: '红包', desc: '红包套餐' }
    ]
    return { iconsList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/variables.scss';
@import '../../style/mixins.scss';

.position {
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  color: $content-fontcolor;
  @include ellipsis;
  .position__icon {
    position: relative;
    top: .02rem;
    font-size: .2rem;
  }
  .position__notice {
    position: absolute;
    right: 0;
    top: .17rem;
    font-size: .2rem;
  }
}
.search {
  margin-bottom: .12rem;
  line-height: .32rem;
  background-color: #f5f5f5;
  color: #b7b7b7;
  border-radius: .16rem;
  font-size: .14rem;
  .iconfont {
    font-size: .2rem;
    display: inline-block;
    position: relative;
    top: .03rem;
    padding: 0 .03rem 0 .16rem;
  }
}
.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;
  &__img {
    width: 100%;
  }
}
.icons {
  display: flex;
  flex-wrap: wrap;
  margin-top: .16rem;
  &__item {
    width: 20%;
    &__img {
      display: block;
      width: .4rem;
      height: .4rem;
      margin: 0 auto;
    }
    &__desc {
      margin: .06rem 0 .16rem 0;
      text-align: center;
      color: $content-fontcolor;
    }
  }
}
.gap {
  height: .1rem;
  background-color: $content-bgcolor;
  margin: 0 -.18rem;
}
</style>
