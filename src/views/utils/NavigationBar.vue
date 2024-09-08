<script setup>
import { useTheme } from 'vuetify'
import { shallowRef, ref, computed } from 'vue'
const theme = useTheme()

const emit = defineEmits(['themeChange'])
const drawer = shallowRef(false)
const items = [
  {
    text: 'Home',
    to: '/',
  },
  {
    text: 'About Us',
    to: '/about',

  },
  {
    text: 'NCB Bands',
    to: '/bands',
  },
  {
    text: 'Concerts and Community',
    to: '/events',
  },
  {
    text: 'Support the NCB',
    to: '/contact',
  },
  {
    text: 'Band Members',
    to: '/band',
  },
  {
    text: 'Media',
    to: '/media',
  }

]
const currentMode = computed(() => {
  return theme.global.current.value.dark ? 'dark' : 'light'
})
const dynamicNavTextColor = computed(() => {
  return theme.global.current.value.dark ? 'nassau-white' : 'nassau-blue'
})
const switchLabel = computed(() => {
  console.log('theme.global.name',theme.global.name.value)
  return  theme.global.name.value === 'dark' ?'Switch to Light Mode':' Switch to Dark Mode'
});
function toggleTheme () {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
  emit('themeChange', currentMode.value)
}
</script>
<template>
  <v-layout class="mb-15">
    <v-navigation-drawer v-model="drawer" color="primary" disable-resize-watcher >

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
        src="/ncbHeader.svg"
        class="mt-1"
        style="height: 100px; width: 100px"
      />
      <div class="ml-3 header-text" ><h1 :class="dynamicNavTextColor" class="text-h2">Nassau Community Bands</h1>
        <p :class="dynamicNavTextColor" class="text-subtitle-2 mt-0">Nassau County,Florida - Amelia Island, Fernandina Beach, Yulee, North Jacksonville, South East
          Georgia</p>
      </div>
      <v-spacer></v-spacer>
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
      <v-btn size="large" :icon="`${currentMode === 'dark' ? 'mdi-weather-sunny':'mdi-moon-waning-crescent'}`" density="comfortable" @click="toggleTheme" :aria-label="switchLabel">
      </v-btn>
      <!--<v-switch-->
      <!--  :value="switchLabel"-->
      <!--  @change="toggleTheme"-->
      <!--  :label="`toggle view mode`"-->
      <!--&gt;</v-switch>-->
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
<style>
.header-text .nassau-white {
    color: #fff
  }
.header-text .nassau-blue {
    color: #001F5A
  }

</style>
