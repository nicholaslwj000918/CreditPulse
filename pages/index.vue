<template lang="pug">

</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      // logoPath: require('../assets/logo/FincareLogo2.png')
    }
  },
  created () {
    setTimeout(() => this.$router.push({ path: '/creditpulse' }), 1000)
  },
  methods: {

  }
}
</script>
