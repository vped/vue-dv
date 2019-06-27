<template lang="pug">
v-container.my-dashboard(
  fluid
  fill-height
  text-xs-center
  v-bind:grid-list-sm="$vuetify.breakpoint.smAndDown"
  v-bind:grid-list-lg="$vuetify.breakpoint.mdAndUp"
)
  v-layout(row wrap)
</template>

<script>
import store from './store' // eslint-disable-line no-unused-vars

export default {
  name: 'Dashboard',

  components: {

  },

  data () {
    return {
      test: this.$store.state.dashboard.test,
      date: '2018-05-21'
    }
  },

  mounted () {
  },

  methods: {
    updateTest () {
      this.test++
      this.$store.dispatch('dashboard/updateTest', this.test)
    },
    functionEvents (date) {
      const [,, day] = date.split('-')
      return parseInt(day, 10) % 3 === 0
    }
  }
}
</script>

<style lang="stylus">
.my-dashboard

  &__media
    height: 100%
    margin: 0

  .picker__title
    display: none !important

</style>
