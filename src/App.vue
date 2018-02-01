<template>
  <div id="app">
    <div class="navbar has-shadow">
      <div class="container">
        <div class="navbar-brand">
          <a href="#" class="navbar-item">MyCompany</a>

        <button class="button navbar-burger" @click="toggleNav" :class="{'is-active' : isActive}">
          <span></span>
          <span></span>
          <span></span>
        </button>

        </div>

        <div class="navbar-end navbar-menu" :class="{'is-active' : isActive}">

          <router-link to="/" class="navbar-item r-item">Home</router-link>
          <router-link to="faq" class="navbar-item r-item">Features</router-link>
          <router-link to="faq" class="navbar-item r-item">About</router-link>
          <router-link to="faq" class="navbar-item r-item">FAQ</router-link>

          <div class="navbar-item">
            <p class="control">
              <a href="#" class="button is-primary is-outlines">
                <span class="icon">
                  <i class="fa fa-download"></i>
                </span>
                <span>Join Now</span>
              </a>
            </p>
          </div>

        </div>

      </div>
    </div>
    <transition name="fade" appear>
      <router-view/>
    </transition>

    <footer class="footer is-primary">
      <div class="container">
        <div class="columns">
          <div class="column">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing.</p>
          </div>
          <div class="column has-text-right">
            <a href="#" class="icon">
              <i class="fa fa-facebook"></i>
            </a>
            <a href="#" class="icon">
              <i class="fa fa-twitter"></i>
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isActive: false
    }
  },
  methods: {
    toggleNav: function() {
      this.isActive = !this.isActive
    }
  }
}
</script>

<style lang="sass">
@import '../node_modules/bulma/bulma.sass'
@import 'mq'

.navbar
  background-color: #383838
  a:hover
    color: gray

.navbar-brand a 
  color: #fff
  font-weight: bold

a.r-item
  color:#C1C1C1
  padding: 0.5rem 1.75rem
  +mobile
    color: gray
    &:hover
      background-color: #F1F1F1

.navbar-burger span
  background-color: #C1C1C1

footer
  background-color: $primary !important
  color: #fff

  .icon
    color: #fff
    margin-left: 20px

.fade-enter-active, .fade-leave-active 
  transition: opacity .5s

.fade-enter, .fade-leave-to
  opacity: 0

</style>
