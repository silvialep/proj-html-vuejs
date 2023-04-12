<script>


export default {

    name: 'CardItem',

    data() {
        return {

        }
    },

    props: {
        img: String,
        text: String,
        link: String,
    },

    emits: [

    ],

    components: {
    },


    computed: {
    },



}


</script>

<template>
    <div class="jumbo-card-item">
        <img :src="img" alt="">
        <span> {{ text }} </span>
        <a href=""> {{ link }} </a>

    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.jumbo-card-item {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;

    img {
        height: 100%;
    }

    a {
        color: rgb(179, 183, 172);
    }
}

</style>