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
        jumboLink: Object,
        isLink: Boolean,
        isIcon: Boolean,
        isHeader: Boolean,
        dropDown: Boolean,
        isJumbo: Boolean,
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

        <div class="nav-link" v-if="isLink == true"> {{ singleLink }} <i class="fa-solid fa-angle-down" v-if="dropDown == true"></i></div>
        
        <i :class="`fa-brands ${singleIcon}`" v-if="isIcon == true"></i>
        
        <i :class="`fa-solid ${singleIcon}`" v-if="isHeader == true"></i>

        <div class="jumbo-nav" v-if="isJumbo == true">
            <i :class="`fa-solid ${jumboLink.icon}`"></i>
            <span> {{ jumboLink.text }} </span>
        </div>


</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.nav-link {
    display: flex;
    align-items: center;
    gap: 5px;
}
.jumbo-nav {
    display: flex;
    align-items: center;
    gap: 10px;
}


</style>