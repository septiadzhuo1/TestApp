<template>
    <v-col :cols="4">
        <v-card
            border="left"
            colored-border
        >    
            <v-card-title> <nuxt-link :to="'post/' + post.id">{{post.title}}</nuxt-link> </v-card-title>
            <v-card-subtitle >{{post.body | truncate(150)}}</v-card-subtitle>
            <v-card-actions>
                <v-spacer></v-spacer>

                <v-btn icon>
                <v-icon>mdi-heart</v-icon>
                </v-btn>

                <v-btn icon>
                <v-icon>mdi-bookmark</v-icon>
                </v-btn>

                <v-btn icon>
                <v-icon>mdi-share-variant</v-icon>
                </v-btn>
            </v-card-actions>
        </v-card>
    </v-col>
</template>

<script lang="ts">
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'
export default {
    props:['post'],
    filters: {
        truncate(string:string, value:number) {
            return string.substring(0, value) + '…';
        }
    }

}
</script>
