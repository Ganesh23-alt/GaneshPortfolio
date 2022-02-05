<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>Web</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="project.dialog"
        lazy
        max-width="1000"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-hover v-slot="{ hover }">
            <v-card hover flat color="transparent">
              <v-img
                :src="project.poster"
                :alt="project.title"
                height="230"
                lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
              <v-card-title primary-title class="justify-center">
                 <v-expand-transition >
          <div v-if="hover" >
            <v-btn large  dark color="green">
              Demo
            </v-btn>
          </div>
        </v-expand-transition>
              </v-card-title>
            </v-card>
              </v-hover>
          </v-flex>

        </template>
        <v-card v-if="project.dialog">
          <v-img :src="project.poster"></v-img>
          <v-card-text>
            <h3 class="headline mb-0">
              <span>Technology</span>
            </h3>
            <v-chip color="green" text-color="white">{{project.tech.tech1}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech2}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech3}}</v-chip>
            <v-chip color="green" text-color="white">{{project.tech.tech4}}</v-chip>
          </v-card-text>
          <v-card-actions>
            <v-btn flat large dark color="green" :href="project.git" target="_blank">
              <v-icon left>fab fa-github</v-icon>GitHub
            </v-btn>
            <v-btn large flat dark color="green" :href="project.demo" target="_blank">
              <v-icon left>fas fa-desktop</v-icon>Demo
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: "Web Portfolio",
  },
  data() {
    return {
      dialog: false,
      projects: [
         {
          dialog: false,
          title: "Grocery E-commerce",
          git: "https://github.com/Ganesh23-alt/VuetifyHomeShop",
          demo: "https://vuetify-home-shop.vercel.app/",
          tech: {
            tech1: "HTML",
            tech2: "CSS",
            tech3: "Vue.js",
            tech4: "Laravell"
          },
          poster: "https://i.imgur.com/CNStArM.png"
        },
        {
          dialog: false,
          title: "Clothing E-commerce",
          git: "https://github.com/Ganesh23-alt/HomeShop",
          demo: "https://ganesh23-alt.github.io/HomeShop/",
          tech: {
            tech1: "HTML",
            tech2: "CSS",
            tech3: "JQuerry",
            tech4: "JavaScript"
          },
          poster: "https://i.imgur.com/23O4Urr.png"
        },
        {
          dialog: false,
          title: "This Site",
          git: "https://github.com/Ganesh23-alt/GaneshPortfolio",
          demo: "https://ganesh-portfolio.vercel.app/",
          tech: {
            tech1: "VUE",
            tech2: "CSS",
            tech3: "HTML",
            tech4: "JavaScript"
          },
          poster: "https://i.imgur.com/aCKBQcM.png"
        },
        {
          dialog: false,
          title: "Blog Posting",
          git: "https://github.com/Ganesh23-alt/EKBANA-BlogTask",
          demo: "https://post-blog.vercel.app/",
          tech: {
            tech1: "VUE",
            tech2: "CSS",
            tech3: "HTML",
            tech4: "JavaScript"
          },
          poster: "https://i.imgur.com/vlCDD0C.png"
        },
        {
          dialog: false,
          title: "Hotel Website",
          git: "https://github.com/Ganesh23-alt",
          demo: "https://hotelkrishna.netlify.app/",
          tech: {
            tech1: "VUE",
            tech2: "Python",
            tech3: "Axios",
            tech4: "JavaScript"
          },
          poster: "https://i.imgur.com/WT6LaDG.png"
        },
        {
          dialog: false,
          title: "Furniture Webiste",
          git: "https://github.com/Ganesh23-alt",
          demo: "https://shfurniture.netlify.app/",
          tech: {
            tech1: "VUE",
            tech2: "Python",
            tech3: "HTML",
            tech4: "JavaScript"
          },
          poster: "https://i.imgur.com/RuLZB2c.png"
        },
       
      ]
    };
  }
};
</script>

<style  scoped>
</style>