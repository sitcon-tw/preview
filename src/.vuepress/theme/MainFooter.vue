<template>
  <footer :class="$style.footer">
    <div :class="$style.left">
      <p :class="$style.mobile_hidden">SITCON 學生計算機年會</p>
      <p>Student information technology conference</p>
      <p :class="$style.mobile_hidden">友站連結</p>
    </div>
    <div :class="$style.rule" />
    <div :class="$style.right">
      <p :class="$style.mobile_hidden">聯絡籌備團隊</p>
      <p>Mail: contact@sitcon.org</p>
      <p>Facebook: fb.me/sitcontw</p>

      <div :class="$style.social_block">
        <a href="https://www.facebook.com/SITCONtw/" target="_blank">
          <img :src="require('./assets/Facebook.svg')" alt="SITCON-Facebook" />
        </a>
        <a href="https://www.flickr.com/people/sitcon/" target="_blank">
          <img :src="require('./assets/Flickr.svg')" alt="SITCON-Flickr" />
        </a>
        <a href="https://t.me/SITCONgeneral" target="_blank">
          <img :src="require('./assets/Telegram.svg')" alt="SITCON-Telegram" />
        </a>
        <a href="https://twitter.com/sitcontw" target="_blank">
          <img :src="require('./assets/Twitter.svg')" alt="SITCON-Twitter" />
        </a>
        <a href="https://www.youtube.com/user/SITCONArchive" target="_blank">
          <img :src="require('./assets/Youtube.svg')" alt="SITCON-Youtube" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'MainFooter'
}
</script>

<style lang="stylus" module>
@import 'stylus/variable.styl'

.footer
  color #E4E4E4
  height 250px
  background-color #464646
  font-size 0px
  >*
    display inline-block
    vertical-align top
  .left
  .right
    font-size 14px
    width calc(50% - 1px)
    height 100%
    padding 40px
    >p
      margin 6px 0px
  .rule
    width 2px
    height 100%
    padding 40px 0px
    background-color #707070
    background-clip content-box
  .right
    position relative
    .social_block
      position absolute
      bottom 40px
      left 40px
      right 40px
      height 60px
      font-size 0px
      >a
      img
        display block
        display inline-block
        vertical-align top
        width 50px
        height 50px
        padding-right 10px
@media all and (max-width: 1000px)
  .footer
    position relative
    height 200px
    z-index 1
    >*
      display block
    .left
    .right
      width 100%
      height auto
      padding 10px 20px
      .mobile_hidden
        display none
    .rule
      width 100%
      height 2px
      padding 0px 20px
    .right
      position static
      .social_block
        bottom 10px
        left 20px
        height 60px
</style>
