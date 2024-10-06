<script setup>
import { ref } from 'vue'
const members = ref([
  {
    name: 'Stephen Hanner',
    role: 'Alto,Tenor Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Larry Blaustein',
    role: 'Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Sara Larrimore',
    role: 'Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Ken Sanders',
    role: 'Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Johnnie Robinson',
    role: 'Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Mark Moore',
    role: 'Trumpet',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'Buddy Drewry',
    role: 'Trumpet',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'Brian Tomlinson',
    role: 'Trumpet',
    image: '/band_members/bryantomlinson.jpg'
  },
  {
    name: 'Bruce Byrd',
    role: 'Trumpet',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'Jim Hinchee',
    role: 'Trumpet',
    image: '/band_members/jim_hinchee.jpeg'
  },
  {
    name: 'Markus Dickman',
    role: 'Director, Lead Trombone',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'Steve Whitman',
    role: 'Tuba',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'Lyle Thompson',
    role: 'Tuba/Trombone',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'Bill Bishop',
    role: 'Trombone',
    image: '/band_members/trombone_placeholder.jpg'
  },
  // {
  //   name: 'John Red',
  //   role: 'Publicity',
  //   image: '/band_members/trombone_placeholder.jpg'
  // },

  {
    name: 'Nora Whittman',
    role: 'Flute',
    image: '/band_members/flute_placeholder.jpg'
  },

  {
    name: 'Sally',
    role: 'Piano/Keyboard',
    image: '/band_members/piano_placeholder.jpg'
  },
  {
    name: 'Richard Whitt',
    role: 'Drums/Percussion',
    image: '/band_members/drumkit_placeholder.jpg'
  },
  {
    name: 'Mike Cifranic',
    role: 'Drums/Percussion',
    image: '/band_members/drumkit_placeholder.jpg'
  },
  {
    name: 'Jim Sadler',
    role: 'Guitar',
    image: '/band_members/jim_square2.jpg',
    background: `url('/band_members/guitar_placeholder.jpg') `
  },
  {
    name: 'Chuck Belinski',
    role: 'Electric Bass',
    image: '/band_members/chuck.jpeg'
  }
])
</script>
<template>
  <v-container>
    <div class="my-10">
      <h1>Band Members</h1>
      <div class="text-center">
        <h2>Jazz Band</h2>
        <v-row>
          <template v-for="(member, i) in members" :key="i">
            <v-col cols="12" md="1">
              <v-hover v-slot="{ isHovering, props }">
                <v-card
                  :class="{ 'on-hover': isHovering }"
                  :elevation="isHovering ? 12 : 2"
                  class="circle-card"
                  v-bind="props"
                >
                  <v-img :lazy-src="member.image" :src="member.image" height="225px" cover>
                    <v-expand-transition>
                      <div
                        v-if="isHovering"
                        class="transition-fast-in-fast-out v-card--reveal align-self-center"
                        style="height: 100%"
                      >
                        {{ member.name }}, {{ member.role }}
                      </div>
                    </v-expand-transition>
                  </v-img>
                </v-card>
              </v-hover>
            </v-col>
          </template>
        </v-row>
      </div>
    </div>
    <div class="my-10">
      <div class="text-center"><h2>Concert Band</h2></div>
    </div>
  </v-container>
</template>

<style lang="scss" scoped>
.v-card {
  transition: opacity 0.4s ease-in-out;
  &.circle-card {
    border-radius: 50%;
    height: 140px;
    width: 140px;
  }
}

.v-card:not(.on-hover) {
  opacity: 0.8;
}
.v-card.on-hover {
  //background-color: grey !important;
  .v-img__img--cover {
    display: none !important;
  }
  .v-card--reveal {
    display: flex !important;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.7);
    color: #fff;
  }
}
</style>
