<template>

    <div>

        <img :src="dettagli.poster" alt="">

        <h5 class="text-center m-2">{{dettagli.title}}</h5>

        <span class="text-center d-block">{{dettagli.author}}</span>

        <span class="text-center d-block">{{dettagli.year}}</span>

    </div>

</template>


<script>

    export default {

        name: 'AlbumCard',

        props: ['dettagli']
        
    }

</script>


<style lang="scss" scoped>

    div {
        
        h5 {
            color: white;
            text-transform: uppercase;
        }

        span {
            color: #808080;
        }

        img{
            width: 100%;
            height: 55%;
            box-shadow: rgba(165, 165, 165, 0.56) 0px 22px 70px 4px;
        }

    }

</style>