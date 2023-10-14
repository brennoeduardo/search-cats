<template>
    <div class="d-flex justify-center pa-2">
        <v-btn append-icon="mdi-cat" @click="getCats" variant="elevated">Buscar novos gatinhos</v-btn>
    </div>
    <v-container>
        <v-row justify="center" class="pa-5">
            <v-col v-for="(cat, index) in cats" :key="index" cols="auto">
                <v-card>
                    <img :src="cat" alt="" width="300">
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import axios from "axios";


export default {
    name: 'TheDog',
    data: () => ({
        cats: [],
        height: 300,
    }),


    beforeMount() {
        this.getCats()
    },

    methods: {
        getCats() {
            axios.get('https://api.thecatapi.com/v1/images/search?limit=10')
                .then(response => {
                    console.log(response);
                    this.cats = response.data.map(cats => cats.url)
                })
        }
    },
}

</script>
<style setup>

main {
background-color: #f5f5f5;
}

</style>