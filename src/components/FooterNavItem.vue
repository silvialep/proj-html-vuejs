<script>


export default {

    name: 'FooterNavItem',

    data() {
        return {

        }
    },

    props: {
        singleLink: String,
        singleIcon: String,
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

        <div> {{ singleLink }} </div>
        <i :class="`fa-brands ${singleIcon}`"></i>


</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;



</style>