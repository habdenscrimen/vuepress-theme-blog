<template>
  <div id="mobile-header">
    <div class="mobile-header-bar">
      <div class="mobile-header-title">
        <NavLink link="/" class="mobile-home-link">{{ $site.title }} </NavLink>
        <SearchBox />
      </div>
    </div>
  </div>
</template>

<script>
import SearchBox from '@SearchBox'

export default {
  components: {
    SearchBox,
  },
}
</script>

<style lang="stylus">
.search-box
  input
    border-radius 5px

.mobile-header-bar
  font-family PT Serif, Serif
  z-index 12
  position fixed
  top 0
  width 100vw
  box-sizing border-box
  background-color $headerBgColor
  margin auto
  box-shadow 0 5px 20px rgba(0, 0, 0, 0.03), 0 6px 6px rgba(0, 0, 0, 0.05)
  transition all 1s cubic-bezier(0.25, 0.8, 0.25, 1)

#mobile-header
  .mobile-header-title
    display flex
    align-items center
    justify-content space-between
    padding 13px 1.2em

    .mobile-home-link
      text-decoration none
      text-transform uppercase
      font-family PT Serif, Serif
      color #222
      font-weight bold

.mobile-nav-item
  padding 10px 0
  list-style none

  a
    text-decoration none

.menu-divider
  margin 0

.mobile-menu-wrapper
  max-height 0
  overflow hidden
  transition 0.3s ease
  background-color $headerBgColor

.mobile-menu-wrapper.open
  max-height 450px
  transition 0.3s ease

@media (min-width: $MQMobile)
  #mobile-header
    display none
</style>
