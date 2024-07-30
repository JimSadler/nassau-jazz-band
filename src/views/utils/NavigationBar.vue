<script setup>
import { shallowRef } from 'vue'

const drawer = shallowRef(false)

const items = [

  {
    text: 'Home',
    to: '/',
  },
  {
    text: 'Band',
    to: '/band',
  },

]
</script>
<template>
  <v-layout class="mb-15">
    <v-navigation-drawer v-model="drawer" color="primary" disable-resize-watcher>
      <v-list nav>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :active="i === 0"
          link
          :to="item.to"
          :title="item.text"
        />
      </v-list>
    </v-navigation-drawer>

    <v-app-bar class="px-md-4">
      <template #prepend>
        <v-app-bar-nav-icon
          v-if="$vuetify.display.smAndDown"
          @click="drawer = !drawer"
        />
      </template>

      <img
        src="/src/assets/noun-jazz-5831284-9B9B9B.svg"
        class="mt-1"
        style="height: 125px; width: 125px"
      />

      <template v-if="$vuetify.display.mdAndUp">
        <v-btn
          v-for="(item, i) in items"
          :key="i"
          :active="i === 0"
          class="me-2 text-none"
          slim
          v-bind="item"
        />
      </template>

      <v-spacer />

      <!--<template #append>-->
      <!--  <v-btn-->
      <!--    class="ms-1"-->
      <!--    color="medium-emphasis"-->
      <!--    icon="mdi-bell-outline"-->
      <!--  />-->

        <!--<v-btn class="ms-1" icon>-->
        <!--  <v-avatar image="https://cdn.vuetifyjs.com/images/john.png" />-->

        <!--  <v-menu activator="parent" origin="top">-->
        <!--    <v-list>-->
        <!--      <v-list-item link title="Update profile" />-->

        <!--      <v-list-item link title="Sign out" />-->
        <!--    </v-list>-->
        <!--  </v-menu>-->
        <!--</v-btn>-->
      <!--</template>-->
    </v-app-bar>

    <!--<v-main height="200">-->
    <!--  &lt;!&ndash;  &ndash;&gt;-->
    <!--</v-main>-->
  </v-layout>
</template>