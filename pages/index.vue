<template>
  <v-app>
    <!-- <v-app-bar app color="primary"> </v-app-bar> -->
    <v-main>
      <div v-for="index in days" :key="index">
        <v-img :src="getUrl(index)" class="ma-2"> </v-img>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    days: 0,
  }),

  mounted() {
    let oneDay = 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
    let firstDate = new Date(2022, 2, 3);
    let secondDate = new Date();

    this.days = Math.round(Math.abs((firstDate - secondDate) / oneDay));

    console.log(this.days);
  },

  methods: {
    getUrl(index) {
      let url = "/photos/pic (" + index + ").JPG";
      return url;
    },
  },
};
</script>
