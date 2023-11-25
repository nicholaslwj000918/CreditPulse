<template lang="pug">
.flex(class="sm:flex-1 sm:items-center sm:justify-end px-4 mt-10")
  div
    nav.isolate.inline-flex.-space-x-px.rounded-md.shadow-sm.pb-8
      a.relative.inline-flex.items-center.rounded-l-md.px-2.py-2.text-gray-400.ring-1.ring-inset.ring-gray-300(class="hover:bg-gray-50 cursor-pointer")
        span Previous
      a.relative.inline-flex.items-center.px-4.py-2.text-sm.font-semibold.text-white(class="bg-primary cursor-pointer") 1
      a.relative.inline-flex.items-center.px-4.py-2.text-sm.font-semibold.text-gray-900.ring-1.ring-inset.ring-gray-300(class="hover:bg-gray-50 cursor-pointer") 2
      a.relative.hidden.items-center.px-4.py-2.text-sm.font-semibold.text-gray-900.ring-1.ring-inset.ring-gray-300(class="hover:bg-gray-50 md:inline-flex cursor-pointer") 3
      a.relative.inline-flex.items-center.rounded-r-md.px-2.py-2.text-gray-400.ring-1.ring-inset.ring-gray-300(class="hover:bg-gray-50 cursor-pointer")
        span Next
</template>

<script>
export default {
  name: 'PaginateComp',
  components: {},
  data () {
    return {}
  }
}
</script>
<style scoped>
.bg-primary {
  background-color: #002147;
}
</style>
