<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="store.toggleLeftDrawer()"
          icon="menu"
          aria-label="Menu"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="store.leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">Essential Links</q-item-label>
        <essential-link
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
import Component from 'vue-class-component';
import Vue from 'vue'
import LayoutStoreModule from './LayoutStoreModule';
import { getModule } from 'vuex-module-decorators';
import EssentialLink from 'src/components/EssentialLink';


@Component({
  components: { EssentialLink }
})
export default class MainLayout extends Vue {

  store = getModule(LayoutStoreModule)

  // components: {
  //   EssentialLink,
  // },
  //
  // data() {
  //   return {
  //     leftDrawerOpen: false,
  essentialLinks = [
    {
      title: 'Docs',
      caption: 'quasar.dev',
      icon: 'school',
      link: 'https://quasar.dev',
    },
    {
      title: 'Discord Chat Channel',
      caption: 'chat.quasar.dev',
      icon: 'chat',
      link: 'https://chat.quasar.dev',
    },
    {
      title: 'Forum',
      caption: 'forum.quasar.dev',
      icon: 'record_voice_over',
      link: 'https://forum.quasar.dev',
    },
    {
      title: 'Twitter',
      caption: '@quasarframework',
      icon: 'rss_feed',
      link: 'https://twitter.quasar.dev',
    },
    {
      title: 'Facebook',
      caption: '@QuasarFramework',
      icon: 'public',
      link: 'https://facebook.quasar.dev',
    },
  ]
  //   };
  // },
};
</script>
