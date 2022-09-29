<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          יער רמת אלון
        </q-toolbar-title>

        <q-btn flat round dense icon="my_location"
          type="a" :href="Globals.map_url"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          לינקים
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue'
import Globals from 'src/globals'

const linksList = [
  {
    title: 'מסלולים',
    caption: 'israelhiking',
    icon: 'map',
    link: 'https://israelhiking.osm.org.il/map/17.44/32.7702/35.0136'
  },
  {
    title: 'ירוק בלב',
    caption: 'yarokbalev.org',
    icon: 'favorite',
    link: 'https://www.yarokbalev.org/%D7%94%D7%A2%D7%9E%D7%95%D7%AA%D7%94/%D7%A4%D7%A2%D7%99%D7%9C%D7%95%D7%AA/%D7%A9%D7%9E%D7%99%D7%A8%D7%AA-%D7%98%D7%91%D7%A2/%D7%A4%D7%90%D7%A8%D7%A7-%D7%A8%D7%9E%D7%AA-%D7%90%D7%9C%D7%95%D7%9F/'
  },
  {
    title: 'דרגו אותנו',
    caption: 'google.com',
    icon: 'star',
    link: 'https://g.co/kgs/rVgPC2'
  },
  /*
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
  */
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      Globals
    }
  }
})
</script>
