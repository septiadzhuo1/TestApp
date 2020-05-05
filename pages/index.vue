<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
    >
      <v-container>
            <PageLoad v-if="loading"/>

        <v-row>
         <Posts v-for="post in posts" :post="post" :key="post.id"/>
        </v-row>
      </v-container>
    </v-flex>
  </v-layout>
</template>

<script lang='ts'>

import Vue, { PropOptions } from 'vue'
import Posts from '~/components/Posts.vue'
import PageLoad from "~/components/PageLoad.vue";
import axios from "axios";
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default Vue.extend({
  data() {
    return {
      posts: [],
      loading:true
    };
  },
  components: {
    Posts,
    PageLoad
  },
  async created() {
    const JsonConfig= {
      headers: {
        Accept: "application/json"
      }
    };
    try{
      const res = await axios.get("https://jsonplaceholder.typicode.com/posts", JsonConfig);
      this.posts = res.data;
      this.loading=false;
    }catch (err) {
      console.log(err);
    }
  }
})
</script>
