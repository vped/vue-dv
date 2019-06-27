<template lang="pug">

</template>

<script>
export default {
  name: 'DefaultSnackbar',

  data () {
    return {
    }
  },

  computed: {
    snackbarActive: {
      get () {
        return this.$store.state.common.snackbar.show
      },
      set (val) {
        this.$store.dispatch('common/updateSnackbar', { show: val })
      }
    }
  }
}
</script>

<style lang="stylus">

</style>
