<template>
  <header>
    <nav :class="$style.navbar">
      <router-link :class="$style.logo" to="/">
        <img :src="require('./assets/SITCON-logo.svg')" alt="sitcon-logo" />
        <h1>SITCON<br>學生計算機年會</h1>
      </router-link>
      <div :class="$style.nav_items">
        <router-link to="/announcement/">最新公告</router-link>
        <router-link to="/activity/">近期活動</router-link>
        <a href="https://shopee.tw/tiwb_" target="_blank">SITCON 販賣部</a>
        <router-link to="/open/">公開資訊</router-link>
        <router-link to="/news/">媒體報導</router-link>
        <router-link to="/community/">友好社群</router-link>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'MainNav'
}
</script>

<style lang="stylus" module>
@import 'stylus/variable.styl'

.navbar
  position fixed
  top 0px
  bottom 0px
  left 0px
  width $navbar-width
  height 100%
  background-color $master-color
  text-align center

  .logo
    margin-top 100px
    display block
    text-decoration none
    img
      width $logo-size
      height $logo-size
    h1
      font-size $navbar-font-size
      color $navbar-text-color
      text-decoration none

  .nav_items
    margin-top 100px
    a
      display block
      padding 8px
      color $navbar-text-color
      font-size $navbar-font-size
      text-decoration none


</style>

