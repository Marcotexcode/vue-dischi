<template>

    <div class="container-fluid p-3">

        <div class="row justify-content-between p-5" v-if="!caricamento">

            <AlbumCard v-for="(elementi, index) in listAlbum" :key="index" :dettagli="elementi" class="col-2 alb m-3 p-4"/>
   
        </div>

        <div v-else>
            <Caricamento/>
        </div>
    </div>

</template>


<script>

    import axios from 'axios';
    import AlbumCard from '@/components/AlbumCard.vue';
    import Caricamento from '@/components/Caricamento.vue';


    export default {

        name: 'Main',

        components: {

            AlbumCard,
            Caricamento

        },

        data() {

            return {

                apiURL : 'https://flynn.boolean.careers/exercises/api/array/music',

                listAlbum : '',

                caricamento: true

            }

        },

        created() {

            this.getListAlbum();

        },

        methods: {

            getListAlbum() {

                axios.get(this.apiURL).then(response => {

                    this.listAlbum = response.data.response;

                    this.caricamento = false;

                })

                .catch(error => {

                    console.log('Errore: ', error);

                })

            }
    
        }

    }

</script>


<style lang="scss" scoped>

    .container-fluid {      
        background-color: #1e2d3b;

        .alb{      
            background-color: #2e3a46;
        }

    }

</style>