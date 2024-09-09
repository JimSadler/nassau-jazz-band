<script>
export default {}
</script>
<template>
  <v-container>
    <div class="my-10">
      <div class="text-center"><h2>Concert Band</h2></div>
      <v-row class="mt-2">
        <v-col cols="1"></v-col>
        <v-col cols="5">
          <v-carousel height="400" hide-delimiters show-arrows="hover" cycle continuous>
            <v-carousel-item src="/concert_band_photos/concert_band_0.jpg" cover></v-carousel-item>
            <v-carousel-item src="/concert_band_photos/concert_band_1.jpg" cover></v-carousel-item>
            <v-carousel-item src="/concert_band_photos/concert_band_2.jpg" cover></v-carousel-item>
            <v-carousel-item src="/concert_band_photos/concert_band_3.jpg" cover></v-carousel-item>
            <v-carousel-item src="/concert_band_photos/concert_band_4.jpg" cover></v-carousel-item>
            <v-carousel-item src="/concert_band_photos/concert_band_5.jpg" cover></v-carousel-item>
          </v-carousel>
        </v-col>
        <v-col>Text</v-col>
        <v-col cols="2"></v-col>
      </v-row>
    </div>
    <div class="my-10">
      <div class="text-center"><h2>Jazz Band</h2></div>
      <v-row class="mt-2">
        <v-col cols="1"></v-col>
        <v-col cols="5">
          <v-carousel
            height="400"
            hide-delimiters
            show-arrows="hover"
            cycle
            continuous
            interval="10000"
          >
            <v-carousel-item src="/jazz_band_photos/jazz_band_4.jpg" cover></v-carousel-item>
            <v-carousel-item src="/jazz_band_photos/jazz_band_3.jpg" cover></v-carousel-item>
            <v-carousel-item src="/jazz_band_photos/jazz_band_2.jpg" cover></v-carousel-item>
            <v-carousel-item src="/jazz_band_photos/jazz_band_1.jpg" cover></v-carousel-item>
            <v-carousel-item src="/jazz_band_photos/jazz_band_0.jpg" cover></v-carousel-item>
            <v-carousel-item src="/jazz_band_photos/jazz_band_5.jpg" cover></v-carousel-item>
          </v-carousel>
        </v-col>
        <v-col>Text</v-col>
        <v-col cols="2"></v-col>
      </v-row>
    </div>
  </v-container>
</template>

<style lang="scss" scoped></style>
