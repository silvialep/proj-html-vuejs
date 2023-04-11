<script>


export default {

    name: 'HeaderNavBar',

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

            ]
            
        }
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
    <nav>
        <ul>
            <li v-for="link in menuLinks"> {{ link.title }} <i class="fa-solid fa-angle-down" v-if="link.dropDown == true"></i></li>
        </ul>

    </nav>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

nav {
    @include container();

    justify-content: center;
    align-items: center;
    height: 60px;

    ul {
        display: flex;
        align-items: center;
        gap: 30px;
        list-style-type: none;
        color: rgb(115, 115, 115);
        height: 2rem;

        li {
            display: flex;
            align-items: center;
            gap: 10px;
            height: 100%;

            .fa-solid {
                font-size: 0.8rem;
            }
        }
    }
}

</style>