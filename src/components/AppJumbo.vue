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
                    text: 'See our <strong>store hours</strong> and services',
                },
                {
                    icon: 'fa-check',
                    text: 'We price match to give you the <strong>best deals</strong>',
                },
            ],

            jumboCard: [
                {
                    img: '/food-transparent-5.png',
                    text: 'Get $25 OFF your first purchase of our homemade pet food!',
                    link: 'Visit the shop',
                }
            ],

            jumboTitle: [
                {
                    subtitle: 'Find the best animal supplies',
                    title: 'We know animals are a part of your family, let us help take care of them',
                    button: 'Learn more about us',
                }
            ],
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
        <div class="square first-square">
            <i class="fa-solid fa-id-card-clip"></i>
            <span>Demos</span>
        </div>
        <div class="square second-square">
            <span><small>$</small><strong>39</strong></span>
            <span>On sale</span>
        </div>
        <div id="jumbo-nav-bar">
            <NavBarItem v-for="jumboLink in jumboLinks" :jumboLink="jumboLink" :isJumbo="true"></NavBarItem>
        </div>
        <!-- <img :src="'/dog-walk.jpg'" alt=""> -->
        <div class="dog-image">
            <div id="title-container">
                <CardItem v-for="item in jumboTitle" :subtitle="item.subtitle" :title="item.title" :button="item.button" :isJumboTitle="true"></CardItem>

            </div>

        </div>
        <div id="jumbo-bottom-bar">
            <CardItem v-for="card in jumboCard" :img="card.img" :text="card.text" :link="card.link" :isJumboCard="true"></CardItem>
        </div>
    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#jumbo {
    position: relative;
    min-height: 500px;
    background-color: $primary;
    background-image: url('/bg-transparent-3.png');
    backdrop-filter: 1;
    background-attachment: fixed;
    background-position: top;
    background-repeat: repeat;
    background-size: 15%;

    .square {
        content: '';
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        justify-content: center;
        width: 65px;
        height: 65px;
        position: absolute;
        right: 2%;
        background-color: white;
        border-radius: 8px;
        font-family: sans-serif;

        &.first-square {
            top: 2%;

        }

        &.second-square {
            top: 12%;

            strong {
                font-size: 2rem;
                color: rgb(101, 188, 123);
            }

            small {
                font-size: 1.1rem;
                font-weight: bold;
                vertical-align: top;
                color: rgb(101, 188, 123);
            }
        }

    }

    .dog-image {
        background-image: url('/banner-5-2x-scaled.jpg');
        min-height: 500px;

        background-attachment: fixed;
        background-position:bottom;
        background-repeat: no-repeat;
        background-size: cover;

        #title-container {
            @include container();

            text-shadow: 2px 2px black;
            padding: 100px 0;
        }
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