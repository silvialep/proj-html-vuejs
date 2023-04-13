<script>
import CardItem from './CardItem.vue';
import NavBarItem from './NavBarItem.vue';




export default {

    name: 'BottomMainSection',

    data() {
        return {
            supplies: [
                {
                    subtitle: 'Find the best animal supplies',
                    title: 'Popular accessories',
                    button: 'View all toys accessories',
                },
            ],
            foodArrivals: [
                {
                    subtitle: 'Find the best food',
                    title: 'New food arrival',
                    button: 'View all food products',
                },
            ],

            iconsStrip: [
                {
                    icon: 'fa-truck',
                    text: 'Free worldwide deliveries',
                },
                {
                    icon: 'fa-map',
                    text: 'Find stores near you',
                },
                {
                    icon: 'fa-dollar-sign',
                    text: 'Best prices guaranteed',
                },
                {
                    icon: 'fa-credit-card',
                    text: 'All credit card accepted',
                },
            ],

            newProducts: [
                {
                    image: '/product-8.jpg',
                    title: 'Colored pet bed',
                    price: '$18.00 - $26.00',
                },
                {
                    image: '/product-2.jpg',
                    title: 'Colorful ball set',
                    price: '$29.00',
                },
                {
                    image: '/product-3.jpg',
                    title: 'Dog bone',
                    price: '<small style="text-decoration: line-through; font-size: 0.5rem">$29.00</small> $18.00',
                },
                {
                    image: '/product-4.jpg',
                    title: 'Animal transport bag',
                    price: '$29.00',
                },
                {
                    image: '/product-5.jpg',
                    title: 'Animal transport cage',
                    price: '$35.00',
                },
                {
                    image: '/product-10.jpg',
                    title: 'Closable cat litter',
                    price: '$16.00',
                },
            ],
        }
    },

    props: {

    },

    emits: ['',

    ],

    components: {
    CardItem,
    NavBarItem
},


    computed: {
        proprieta() {
        }
    },



}


</script>

<template>
    <div id="banner-section">
        <div id="left-banner">
            <div class="title-container">
                <CardItem v-for="supply in supplies" :subtitle="supply.subtitle" :title="supply.title" :button="supply.button" :isSectionTitle="true"></CardItem>
            </div>
        </div>

        <div id="right-banner">
            <div class="title-container">
                <CardItem v-for="foodArrival in foodArrivals" :subtitle="foodArrival.subtitle" :title="foodArrival.title" :button="foodArrival.button" :isSectionTitle="true"></CardItem>
            </div>
        </div>
    </div>
    <div id="main-nav-bar">
        <div class="nav-bar-container">
            <NavBarItem v-for="item in iconsStrip" :jumboLink="item" :isMain="true"></NavBarItem>
        </div>
    </div>
    <div id="new-products">
        <div class="title">
            <h3>New products arrivals</h3>
            <span>Latest products</span>
        </div>
        <div class="products-cards">
            <CardItem v-for="card in newProducts" :img="card.image" :title="card.title" :price="card.price" :isNewProducts="true"></CardItem>
        </div>
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#banner-section {
    width: 100%;
    min-height: 500px;
    display: flex;

    #left-banner {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50%;
        background-image: url('/banner-8-2x.jpg');
        background-attachment: initial;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;

        .title-container {
            width: 100%;
            height: 100%;
        }
    }

    #right-banner {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50%;
        background-image: url('/banner-9-2x.jpg');
        background-attachment: initial;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;

        .title-container {
            width: 100%;
            height: 100%;
        }
    }
}

#main-nav-bar {
    @include background-image();
    background-repeat: repeat-x;
    background-size: 20%;
    background-color: $primary;
    min-height: 250px;
    margin-bottom: 100px;

    .nav-bar-container {
        @include container();
        align-items: center;
        justify-content: center;
        display: flex;
        gap: 100px;
        height: 250px;
    }
}

#new-products {
    @include container();
    flex-flow: column;
    align-items: center;
    padding-bottom: 100px;

    .title {
        display: flex;
        flex-flow: column;
        align-items: center;
        justify-content: center;
        gap: 30px;
        margin-bottom: 50px;

        h3 {
            font-size: 2rem;
            font-family: serif;
        }

        span {
            color: $tertiary;
        }
    }

    .products-cards {
        display: flex;
        flex-flow: row wrap;
        gap: 10px;
    }
}

</style>


