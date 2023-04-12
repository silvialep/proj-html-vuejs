<script>

import NavBarItem from './NavBarItem.vue';
import CardItem from './CardItem.vue';



export default {

    name: 'AppJumbo',

    data() {
        return {
            jumboLinks: [
                {
                    icon: 'fa-map',
                    text: '<strong>International</strong> Shipping Services'
                },
                {
                    icon: 'fa-clock',
                    text: 'See our store hours and services',
                },
                {
                    icon: 'fa-check',
                    text: 'We price match to give you the best deals',
                },
            ],

            jumboCard: [
                {
                    img: '/food-transparent-5.png',
                    text: 'Get $25 OFF your first purchase of our homemade pet food!',
                    link: 'Visit the shop',
                }
            ]
        }
    },

    emits: [

    ],

    components: {
    NavBarItem,
    CardItem
},


    computed: {
    },



}


</script>

<template>
    <div id="jumbo">
        <div id="jumbo-nav-bar">
            <NavBarItem v-for="jumboLink in jumboLinks" :jumboLink="jumboLink" :isJumbo="true"></NavBarItem>
        </div>
        <!-- <img :src="'/dog-walk.jpg'" alt=""> -->
        <div class="dog-image">

        </div>
        <div id="jumbo-bottom-bar">
            <CardItem v-for="card in jumboCard" :img="card.img" :text="card.text" :link="card.link"></CardItem>
        </div>
    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#jumbo {
    min-height: 500px;
    background-color: $primary;
    background-image: url('/bg-transparent-3.png');
    background-attachment: fixed;
    background-position: top;
    background-repeat: repeat;
    background-size: 15%;

    .dog-image {
        background-image: url('/dog-walk.jpg');
        min-height: 500px;

        background-attachment: fixed;
        background-position:bottom;
        background-repeat: no-repeat;
        background-size: cover;
    }

    #jumbo-nav-bar {
        @include container();

        justify-content: space-around;
        align-items: center;
        height: 60px;
        color: rgb(179, 183, 172);
        font-size: 0.8rem;
    }

    #jumbo-bottom-bar {
        @include container();

        justify-content: center;
        color: white;
        height: 100px;
    }
}

</style>