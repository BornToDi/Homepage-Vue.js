<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          class="bg-black"
          flat
          @click="drawer = !drawer"
          round
          dense
          icon="menu"
        />
        <!--<q-toolbar-title>Header</q-toolbar-title>-->
        <div class="row col-12">
          <div class="col-9 q-pt-md">
            <div class="text-h4 text-black">
              Control Panel
              <q-badge
                transparent
                align="middle"
                color="green text-black text-weight-bold"
              >
                BRAVE INDICATOR SDN. BHD.
              </q-badge>
            </div>
          </div>
          <!--avator-->
          <div class="col-3 flex">
            <div class="q-ml-lg">
              <q-btn-dropdown
                class="q-ma-sm"
                split
                color="info"
                push
                no-caps
                @click="onMainClick"
              >
                <template v-slot:label>
                  <div class="row items-center no-wrap q-px-md">
                    <div class="text-center text-black">
                      <span class="text-caption q-pa-none">Custom</span> <br />Content
                    </div>
                  </div>
                </template>
              </q-btn-dropdown>
            </div>
            <div class="q-gutter-sm q-pt-md q-pr-lg fixed-right">
              <q-avatar>
                <img src="https://cdn.quasar.dev/img/avatar.png" />
              </q-avatar>
            </div>
          </div>
          <!--finish-->
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
    class="shadow-2 q-pt-lg bg-light-blue-2 rounded-borders"
      v-model="drawer"
      show-if-above
      :width="200"
      :breakpoint="500"
    >
      <q-list>
        <q-item-label
          header
        >
          {{  }}
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
      <q-item class="fixed-bottom q-pa-md" clickable v-ripple>
                  <q-item-section avatar>
                    <q-icon name="logout" />
                  </q-item-section>

                  <q-item-section> Logout </q-item-section>
                </q-item>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Dashboard',
    caption: '',
    icon: 'dashboard',
    link: 'http://localhost:8080/#/dash'
  },
  {
    title: 'Employee',
    caption: '',
    icon: 'people',
    link: 'http://localhost:8080/#/emp'
  },
  {
    title: 'Manager',
    caption: '',
    icon: 'people',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Income',
    caption: '',
    icon: 'monetization_on',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Expense',
    caption: '',
    icon: 'price_change',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Documents',
    caption: '',
    icon: 'description',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Logs',
    caption: '',
    icon: 'receipt_long',
    link: 'https://awesome.quasar.dev'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      drawer: ref(false),
      value: 71,
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
