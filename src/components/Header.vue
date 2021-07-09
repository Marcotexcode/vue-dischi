<template>

    <nav>

        <img src="@/assets/img/logo.png" alt="">

        <SearchGenre />
    </nav>

</template>

<script>

    import SearchGenre from '@/components/SearchGenre.vue';
    


export default {

    name: 'Header',

    components: {

        SearchGenre

    }

}

</script>

<style lang="scss" scoped>
    
    nav{
        background: #2e3a46;
        height: 70px;
        padding: 10px 30px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        img{
            width: 50px;
        }

    }

</style>