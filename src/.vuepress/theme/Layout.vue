<template>
  <div class="theme-container">
    <main-nav v-if="$page.frontmatter.main" />
    <Content :class="{ [$style.nav_open] : $page.frontmatter.main }"/>
    <main-footer v-if="$page.frontmatter.main" :class="{ [$style.nav_open] : $page.frontmatter.main }" />
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
}
</script>

<style lang="stylus">
@import 'stylus/theme.styl'
</style>

<style lang="stylus" module>
@import 'stylus/variable.styl'

.nav_open
  margin-left: $navbar-width
</style>


