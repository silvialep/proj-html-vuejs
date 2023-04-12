<script>


export default {

    name: 'NavBarItem',

    data() {
        return {

        }
    },

    props: {
        singleLink: String,
        singleIcon: String,
        isLink: Boolean,
        isIcon: Boolean,
        isHeader: Boolean,
        dropDown: Boolean,
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

        <div v-if="isLink == true"> {{ singleLink }} <i class="fa-solid fa-angle-down" v-if="dropDown == true"></i></div>
        <i :class="`fa-brands ${singleIcon}`" v-if="isIcon == true"></i>
        <i :class="`fa-solid ${singleIcon}`" v-if="isHeader == true"></i>


</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;



</style>