<script setup>
import { ref } from 'vue'
const members = ref([
  {
    name: 'John Doe',
    role: 'Trumpet',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Jane Doe',
    role: 'Trombone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'John Smith',
    role: 'Saxophone',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Jane Smith',
    role: 'Clarinet',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'John Johnson',
    role: 'Flute',
    image: '/band_members/sax-placeholder.jpg'
  },
  {
    name: 'Jane Johnson',
    role: 'Oboe',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'John Brown',
    role: 'Bassoon',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'Jane Brown',
    role: 'Horn',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'John White',
    role: 'Tuba',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'Jane White',
    role: 'Percussion',
    image: '/band_members/trumpet_placeholder.jpg'
  },
  {
    name: 'John Black',
    role: 'Conductor',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'Jane Black',
    role: 'Assistant Conductor',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'John Green',
    role: 'Librarian',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'Jane Green',
    role: 'Assistant Librarian',
    image: '/band_members/trombone_placeholder.jpg'
  },
  {
    name: 'John Red',
    role: 'Publicity',
    image: '/band_members/trombone_placeholder.jpg'
  },

  {
    name: 'Jane Blue',
    role: 'Assistant Membership',
    image: '/band_members/flute_placeholder.jpg'
  },

  {
    name: 'Jane Yellow',
    role: 'Treasurer',
    image: '/band_members/piano_placeholder.jpg'
  },
  {
    name: 'John Orange',
    role: 'Vice President',
    image: '/band_members/drumkit_placeholder.jpg'
  },
  {
    name: 'Jane Orange',
    role: 'President',
    image: '/band_members/drumkit_placeholder.jpg'
  },
  {
    name: 'John Purple',
    role: 'Webmaster',
    image: '/band_members/guitar_placeholder.jpg'
  },
  {
    name: 'Jane Purple',
    role: 'Assistant Webmaster',
    image: '/band_members/bass_placeholder.jpg'
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
