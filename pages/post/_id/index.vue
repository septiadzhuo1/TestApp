<template>
    <div>
        <v-container>
            <v-card
            border="left"
            colored-border
        >    
            <PageLoad v-if="loading"/>
            <v-card-title> {{post.title}} </v-card-title>
            <v-card-subtitle >
                {{post.body}}
                <br>
             <v-btn small to="/">back</v-btn>
            </v-card-subtitle>
        </v-card>
        </v-container>
    </div>
</template>

<script lang="ts">
import axios from "axios";
import PageLoad from "~/components/PageLoad.vue";

export default ({
    data() {
        return {
            post: [],
            loading:true
        };
    },
    components: {
        PageLoad
    },
    async created() {
        const JsonConfig= {
            headers: {
                Accept: "application/json"
            }
        };
        try{
            const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`, JsonConfig);
            this.post = res.data;
            this.loading = false;
        }catch (err) {
            console.log(err);
        }
    }
})
</script>