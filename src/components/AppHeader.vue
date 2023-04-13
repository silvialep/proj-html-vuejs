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
            activeIndex: 0,
            showMenu: false,
        }
    },

    methods: {
        changeActive(index) {
            this.activeIndex = index;
        },

        changeMenu() {
            this.showMenu = true;
            console.log('funge');
        },

        hideMenu() {
            this.showMenu = false;
        }
    },

    components: {
        NavBarItem,
        HeaderSearchBar,
    },


}


</script>

<template>
    <header>
        <HeaderSearchBar></HeaderSearchBar>
        <hr>
        <!-- <NavBarItem></NavBarItem> -->
        <div class="header-nav-bar">
            <ul>
                <li v-for="(link, index) in menuLinks" :class="activeIndex == index ? 'active' : ''" @click="changeActive(index)"> {{ link.title }} <i class="fa-solid fa-angle-down" @mouseover="changeMenu()" @mouseleave="hideMenu()" v-if="link.dropDown == true"></i>
                    <!-- <div v-if="showMenu == true && " class="show-menu"></div> -->
                </li>
                
            </ul>
            <!-- <NavBarItem v-for="singleLink in menuLinks" :singleLink="singleLink.title" :isLink="true" :dropDown="singleLink.dropDown"></NavBarItem> -->
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
        gap: 40px;

        ul {
            display: flex;
            gap: 30px;
            list-style-type: none;
            color: $linkColor;

            li {
                position: relative;

                &:hover {
                    cursor: pointer;
                    color: black;
                }
            }

            li.active {
                color: black;
            }

            .show-menu {
                position: absolute;
                top: 0;
                width: 40px;
                height: 100px;
                border: 1px solid black;
            }
        }

    }
}

</style>