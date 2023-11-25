<template lang="pug">
TableComp
</template>

<script>
import { mapGetters } from 'vuex'
import TableComp from '~/components/TableComp.vue'

export default {
  name: 'CreditPulse',
  components: {
    TableComp
  },
  layout: 'dashboardLayout',
  data () {
    return {
    }
  },
  computed: {
    ...mapGetters({})
  },
  methods: {}
}
</script>

<style scoped></style>
