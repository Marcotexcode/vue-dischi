<template>

    <div class="container-fluid">

        <div class="row">

            <div v-for="(elementi, index) in listAlbum" :key="index" class="col-3">

                prova

            </div>
            
        </div>

    </div>

</template>

<script>

    import axios from 'axios';

    export default {

        name: 'Main',

        data() {

            return {

                apiURL : 'https://flynn.boolean.careers/exercises/api/array/music',

                listAlbum : []

            }

        },

        created() {

            this.getListAlbum();

        },

        methods: {

            getListAlbum() {

                axios.get(this.apiURL).then(response => {

                    this.listAlbum = response.data.response;

                    console.log(this.ListAlbum);

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
        height: calc(100vh - 70px);
        background-color: #1e2d3b;
    }

</style>