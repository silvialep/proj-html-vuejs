<script>

import HeaderNavBar from "./HeaderNavBar.vue";
import HeaderSearchBar from "./HeaderSearchBar.vue";

export default {

    name: 'AppHeader',

    data() {
        return {

        }
    },

    props: {

    },

    emits: [

    ],

    components: {
        HeaderNavBar,
        HeaderSearchBar,
    },


    computed: {
    },



}


</script>

<template>
    <header>
        <HeaderSearchBar></HeaderSearchBar>
        <hr>
        <HeaderNavBar></HeaderNavBar>
        

    </header>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

header {
    background-color: white;
    display: flex;
    flex-flow: column nowrap;
    width: 100vw;
    height: 120px;

    hr {
        color: rgb(242, 242, 242, .2);
    }
}

</style>