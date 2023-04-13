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
    <!-- lista di link, riutilizzata nell'header e nel footer -->
    <div class="nav-link" v-if="isLink == true"> {{ singleLink }} <i class="fa-solid fa-angle-down" v-if="dropDown == true"></i></div>
    
    <!-- lista di icone nel footer -->
    <i :class="`fa-brands ${singleIcon}`" v-if="isIcon == true"></i>
    
    <!-- lista di icone nell'header -->
    <i :class="`fa-solid ${singleIcon}`" v-if="isHeader == true"></i>

    <!-- lista superiore nel jumbo, con i link inseriti come tag HTML nell'array -->
    <div class="jumbo-nav" v-if="isJumbo == true">
        <i :class="`fa-solid ${jumboLink.icon}`"></i>
        <span v-html="jumboLink.text"></span>
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