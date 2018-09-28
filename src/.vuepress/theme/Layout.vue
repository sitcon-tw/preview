<template>
  <div class="theme-container">
    <main-nav v-if="$page.frontmatter.main" v-model="toggle" />
    <main :class="[{ [$style.nav_open] : !mobile && $page.frontmatter.main }, $style.nav_mobile]">
      <Content :class="$style.content"/>
      <main-footer v-if="$page.frontmatter.main"/>
    </main>
  </div>
</template>
<script>
import MainNav from './MainNav.vue'
import MainFooter from './MainFooter.vue'

export default {
  components: {
    MainNav,
    MainFooter
  },
  data () {
    return {
      toggle: false,
      mobile: false
    }
  },
  mounted () {
    this.mobile = window.matchMedia('(max-width: 1000px)').matches
    window.onresize = () => {
      this.mobile = window.matchMedia('(max-width: 1000px)').matches
    }
  }
}
</script>

<style lang="stylus">
@import 'stylus/theme.styl'
</style>

<style lang="stylus" module>
@import 'stylus/variable.styl'

.nav_open
  margin-left: $navbar-width
@media all and (max-width: 1000px)
  .nav_mobile
    margin-top: 40px
.content
  padding 16px
</style>


