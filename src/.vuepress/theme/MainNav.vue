<template>
  <header>
    <nav :class="[$style.navbar, {[$style.close]: !value}]">
      <router-link :class="$style.logo" to="/">
        <img :src="require('./assets/SITCON-logo.svg')" alt="sitcon-logo" />
        <h1>SITCON<br>學生計算機年會</h1>
      </router-link>
      <div :class="$style.nav_items">
        <router-link
          to="/"
          :class="[$style.main, {[$style.active]: $page.path === '/'}]"
          @click.native="$emit('input', false)">首頁</router-link>
        <template v-for="item in items">
          <router-link
            v-if="!item.path.includes('http')"
            :to="item.path"
            :class="{[$style.active]: $page.path === item.path}"
            @click.native="$emit('input', false)">
            {{ item.name }}
          </router-link>
          <a v-else :href="item.path" target="_blank">{{ item.name }}</a>
        </template>
      </div>
    </nav>
    <div :class="[$style.navbar_btn, {[$style.navbar_btn_close]: !value}]" @click.stop="$emit('input', !value)"></div>
  </header>
</template>

<script>
export default {
  name: 'MainNav',
  props:{
    value: Boolean
  },
  data () {
    return {
      items: [
        {
          name: '最新公告',
          path: '/announcement/',
        },
        {
          name: '近期活動',
          path: '/activity/'
        },
        {
          name: 'SITCON 販賣部',
          path: 'https://shopee.tw/tiwb_'
        },
        {
          name: '公開資訊',
          path: '/open/'
        },
        {
          name: '媒體報導',
          path: '/news/'
        },
        {
          name: '友好社群',
          path: '/community/'
        }
      ]
    }
  }
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
  z-index 100
  transition: all .4s
  .navbar_btn
    display none
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
    .main
      display none
    a
      display block
      padding 8px
      color $navbar-text-color
      font-size $navbar-font-size
      text-decoration none

@media all and (max-width: 1000px)
  .navbar
    padding-left 25px
    background-color #97c59b
    overflow hidden
    .logo
      display none
    .nav_items
      .main
        display block
      a
        text-align left
        position relative
        padding 16px 12px
      .active
        &:before
          content ''
          width 5px
          background-color #71a475
          position absolute
          top 12px
          bottom 12px
          left 0px
  .close
    transform translateX(-100%)
  .navbar_btn
    display block
    width 35px
    height 35px
    background-image url('./assets/sidebar-open.svg')
    background-size contain
    background-position center
    cursor pointer
    position fixed
    top 16px
    left 16px
    z-index 200
  .navbar_btn_close
    background-image url('./assets/sidebar-close.svg')
</style>

