<template lang="pug">
div
  div(:class="[sidebarOpen ? 'w-64 fixed dflex min-h-screen' : 'hidden',' lg:inset-y-0 z-50   lg:flex-col']")
    // Sidebar component
    .dflex.grow.shadow-lg.flex-col.gap-y-5.overflow-y-auto.border-r.border-gray-200.bg-white.px-6.pb-4.rounded-tr-3xl.rounded-br-3xl
      .dflex.h-16.items-center.justify-center
        //Logo Component
        //h1.text-lg.font-bold(class="text-[#112346]") Credit Pulse
      nav.dflex.flex-1.flex-col
        ul.dflex.flex-1.flex-col.gap-y-7(role="list")
          li
            div
            .mt-2.dflex.rounded-xl.shadow-sm
                .relative.dflex.flex-grow.items-stretch(class="focus-within:z-10 ")
                  .pointer-events-none.absolute.inset-y-0.left-0.dflex.items-center.pl-3
                    magnifying.h-5.w-5.text-gray-400
                  input#email.block.w-full.rounded-xl.border-0.pl-10.text-gray-900.ring-1.ring-inset.ring-gray-300(type="email" name="email" class="py-3 bg-secondary placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-blue-500 sm:text-sm sm:leading-6" placeholder="Search")
          li
            ul.-mx-2.space-y-1(role="list")
              li(v-for="item in navigation" :key="item.name")
                a(:href="item.href" :class="[item.current ? 'bg-primary text-white' : 'text-gray-700 cardHover hover:bg-primary hover:text-white', 'group dflex gap-x-3 rounded-md px-2 py-4 items-center text-sm leading-6 font-semibold']")
                  component(:is="item.icon" :class="[item.current ? 'text-white' : 'text-gray-400 group-hover:text-white', ' dflex items-center justify-center']")
                  p {{ item.name }}

          li.mt-auto
            a.group.-mx-2.dflex.items-center.gap-x-3.rounded-md.cardHover.whitespace-nowrap.px-2.py-4.text-sm.font-semibold.leading-6.text-gray-700(href="#" class=" hover:text-white")
              UserIcon.items-center.justify-center.text-gray-400(class="group-hover:text-white")
              p My Profile
  .max-w-full(:class="[sidebarOpen ? 'pl-64' : '' ,' min-h-screen  bg-main']")
    .top-0.dflex.h-16.items-center.justify-between.gap-x-4.px-4(class="sm:gap-x-6 sm:px-6 lg:px-8")
      div.dflex.items-center.gap-4
        span(@click="setSidebar" class="cursor-pointer")
          Bars
        h1.text-lg.font-semibold Dashboard
      div.dflex.items-center.gap-x-6
        Notification
        a.border-2.px-5.dflex.items-center.gap-2.border-primary.font-semibold.rounded-full(class="py-1 border-[#002147] text-[#002147]")
          UserIcon
          span(class="lg:block hidden") Nicholas Lee
    Nuxt
</template>

<script>
import { mapGetters } from 'vuex'
import HomeIcon from '../icons/HomeIcon.vue'
import InsightsIcon from '../icons/InsightsIcon.vue'
import UserIcon from '../icons/UserIcon.vue'
import Magnifying from '../icons/MagnifyingIcon.vue'
import Bars from '../icons/BarsIcon.vue'
import Notification from '../icons/NotificationIcon.vue'
import DummyUser from '../icons/DummyUser.vue'
import TrendListVue from '~/components/dashboard/trendList.vue'
import UpperTitleVue from '~/components/UpperTitle.vue'
import StartupTableVue from '~/components/dashboard/startupTable.vue'
import TableComp from '~/components/TableComp.vue'

export default {
  name: 'DashboardPage',
  components: {
    UpperTitleVue,
    TrendListVue,
    StartupTableVue,
    Magnifying,
    Bars,
    Notification,
    HomeIcon,
    DummyUser,
    UserIcon,
    TableComp
  },
  layout: 'default',
  data () {
    return {

      navigation: [
        { name: 'Dashboard', icon: HomeIcon, current: true },
        { name: 'Customers', icon: InsightsIcon, current: false }
      ],

      sidebarOpen: true
    }
  },
  computed: {
    ...mapGetters({})
  },
  methods: {
    setSidebar () {
      this.sidebarOpen = !this.sidebarOpen
    }
  }
}
</script>

<style scoped>
.dflex {
  display: flex !important;
}
.bg-primary {
  background-color: #112346 !important;
}
.cardHover:hover {
  background-color: #112346 !important;
}
.bg-secondary {
  background-color: rgb(0 33 71 / 0.05) !important;
}
.bg-main {
  background-color: #f2f4f6 !important;
}
</style>
