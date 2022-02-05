<template>
<kinesis-container>
  <v-container grid-list-xl>
     
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span>My</span>
          <span class="green--text">Services</span>
        </h2>
      </v-flex>
      
  
      <v-flex v-for="service in services" :key="service.src" xs6 sm3 md3 lg3 xl3>
            <vue-flashcard>
        <kinesis-element :strength="30" type="depth">
        <v-card hover flat color="transparent" :style="{'cursor':'context-menu'}">
          <v-card-title></v-card-title>
          <v-img
            :src="service.src"
            height="100"
            aspect-ratio="2.75"
            :alt="'Ganesh do '+service.title"
            lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
            contain
          ></v-img>
          <v-card-title class="justify-center">
            <v-flex text-xs-center subheading font-weight-bold>{{service.title}}</v-flex> 
           
          </v-card-title>
        </v-card>
        </kinesis-element>
        </vue-flashcard>
      </v-flex>

      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span>My</span>
          <span class="green--text">Clients</span>
        </h2>
      </v-flex>

      <v-flex v-for="client in clients" :key="client.src" xs6 sm4 md3 lg2 xl2>
         <kinesis-element :strength="20" type="depth">
        <v-card flat :href="client.href" target="_blank" color="transparent">
          <v-hover>
            <v-img
              slot-scope="{ hover }"
              :src="client.src"
              :alt="client.name+' logo'"
              lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
              height="100"
              width="160"
              aspect-ratio="2.75"
              contain
            >
              <v-expand-transition>
                <div
                  v-if="!hover"
                  class="transition-fast-in-fast-out green v-img--reveal"
                  style="height: 100%;"
                ></div>
              </v-expand-transition>
            </v-img>
          </v-hover>
        </v-card>
         </kinesis-element >
      </v-flex>
    </v-layout>
  </v-container>
</kinesis-container>
</template>

<script>
import {KinesisContainer , KinesisElement} from 'vue-kinesis';
// import vueFlashcard from 'vue-flashcard';
export default {
  components:{
    // vueFlashcard,
  },
  metaInfo: {
    title: "Ganesh's Services",
  },
  data() {
    return {
      clients: [
        {
          name: "HomeShop",
          src: "https://i.imgur.com/CNStArM.png",
          href: "#"
        },
        {
          name: "HamroChulo",
          src: "https://i.imgur.com/23O4Urr.png",
          href: "#"
        },
        {
          name: "GeccoDev",
          src: "https://i.imgur.com/aCKBQcM.png",
          href: "#"
        },
        {
          name: "HotelKrishna",
          src: "https://i.imgur.com/vlCDD0C.png",
          href: "#"
        },
        {
          name: "SH Furniture",
          src: "https://i.imgur.com/WT6LaDG.png",
          href: "#"
        },
        {
          name: "Omlot",
          src: "https://i.imgur.com/RuLZB2c.png",
          href: "#"
        }
      ],
      services: [
        {
          src: "https://i.imgur.com/GvTt5GG.png",
          title: "Web Development"
        },
        {
          src: "https://i.imgur.com/g74mGuU.png",
          title: "Web Design"
        },

        {
          src: "https://i.imgur.com/wXLtLKy.png",
          title: "Web Deployment"
        },
      ],
    };
  }
};
</script>
<style >
.v-img--reveal {
  opacity: 0.3;
}
</style>