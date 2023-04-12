<script>

import HeaderSearchBar from "./HeaderSearchBar.vue";
import NavBarItem from "./NavBarItem.vue";

export default {

    name: 'AppHeader',

    data() {
        return {
            menuLinks: [
                {
                    title: 'Home',
                    contents: [
                    ],
                    dropDown: true,
                },
                {
                    title: 'Shop',
                    contents: [
                    ],
                    dropDown: true,
                },
                {
                    title: 'About',
                    contents: [
                    ],
                    dropDown: false,
                },
                {
                    title: 'Blog',
                    contents: [
                    ],
                    dropDown: false,
                },
                {
                    title: 'Contact',
                    contents: [
                    ],
                    dropDown: false,
                },
                {
                    title: 'Shop by brand',
                    contents: [
                    ],
                    dropDown: true,
                },

            ],
        }
    },

    props: {

    },

    emits: [

    ],

    components: {
        NavBarItem,
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
        <!-- <NavBarItem></NavBarItem> -->
        <div class="header-nav-bar">
            <NavBarItem v-for="singleLink in menuLinks" :singleLink="singleLink.title" :isLink="true" :dropDown="singleLink.dropDown"></NavBarItem>

        </div>

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

    .header-nav-bar {
        @include container();

        justify-content: center;
        align-items: center;
        height: 60px;
        gap: 30px;
        color: rgb(115, 115, 115);

    }
}

</style>