<script>

import CardItem from './CardItem.vue';
import NavBarItem from './NavBarItem.vue';



export default {

    name: 'TopMainSection',

    data() {
        return {
            indice: 0,
            productsCategories: [
                {
                    category: 'Bed',
                    img: [
                        '/product-9.jpg', 
                        '/product-8.jpg'
                    ],
                },
                {
                    category: 'Food',
                    img: [
                        '/product-3.jpg'
                    ],
                },
                {
                    category: 'Toys',
                    img: [
                        '/product-2.jpg'
                    ],
                },
                {
                    category: 'Transport',
                    img: [
                        '/product-4.jpg', 
                        '/product-5.jpg', 
                        '/product-10.jpg', 
                        '/product-16.jpg'
                    ],
                },
            ],

            foods: [
                {
                    title: 'Kibble',
                    description: 'Dry dog food',
                    image: '/food-transparent-18.png',
                    button: 'Shop dry food',
                },
                {
                    title: 'Moist',
                    description: 'Canned dog food',
                    image: '/food-transparent-17.png',
                    button: 'Shop moist food',
                },
                {
                    title: 'Frozen',
                    description: 'Freeze-Dried dog food',
                    image: '/food-transparent-16.png',
                    button: 'Shop frozen food',
                },
            ],

            newArrivals: [
                {
                    subtitle: 'Find the best animal supplies',
                    title: 'New Arrivals weekly',
                    button: 'Learn more about us',
                },
            ],

            itemsSection: [
                {
                    subtitle: 'All-time best sellers',
                    title: 'Items everyone loves',
                    button: 'View all products',
                },
            ],

            itemsCards: [
                {
                    image: '/product-21.jpg',
                    title: 'Transport cage',
                    price: '$25.00',
                },
                {
                    image: '/product-20.jpg',
                    title: 'Dog leash',
                    price: '$25.00',
                },
                {
                    image: '/product-16.jpg',
                    title: 'Animal transport cage',
                    price: '<small style="text-decoration: line-through; font-size: 0.5rem">$35.00</small> $25.00',
                },
                {
                    image: '/product-11.jpg',
                    title: 'Colorful cat leash',
                    price: '$12.00',
                },
            ],
        }
    },

    props: {

    },

    components: {
    CardItem,
    NavBarItem
},


    computed: {
    },



}


</script>

<template>
    <div class="section-container">
        <div id="categories">
            <div id="section-title">
                <h2>Browse by category</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Enim excepturi placeat quisquam nobis, deleniti in aliquam recusandae eveniet commodi et possimus minima incidunt tempore neque aliquid dolorem quaerat ad sunt.</p>
            </div>
            <div class="products-cards">
                <CardItem v-for="product in productsCategories" :list="product.img.length" :category="product.category" :img="product.img[indice]" :isProducts="true" :isOnlyProducts="true"></CardItem>
            </div>
            <div class="foods-cards">
                <CardItem v-for="food in foods" :isFood="true" :title="food.title" :subtitle="food.description" :img="food.image" :button="food.button" ></CardItem>
            </div>
            <div class="new-arrivals">
                <div class="new-arr-card">
                    <CardItem v-for="item in newArrivals" :subtitle="item.subtitle" :title="item.title" :button="item.button" :isSectionTitle="true"></CardItem>
                </div>

            </div>
            <div class="items-section">
                <CardItem v-for="section in itemsSection" :subtitle="section.subtitle" :title="section.title" :button="section.button" :isItemsTitle="true"></CardItem>
            </div>
            <div class="item-cards">
                <CardItem v-for="itemCard in itemsCards" :img="itemCard.image" :title="itemCard.title" :price="itemCard.price" :isProducts="true" :isOnlyItems="true"></CardItem>
            </div>

        </div>

    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.section-container {
    background-color: white;

    #categories {
        @include container();

        flex-flow: column nowrap;

        #section-title {
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            justify-content: center;
            gap: 30px;
            margin: 100px auto 80px;
            width: 60%;
            font-family: serif;

            h2 {
                font-size: 2.5rem;
                font-weight: lighter;
            }

            p {
                font-family: sans-serif;
                line-height: 2rem;
                text-align: center;
            }
        }

        .products-cards, .foods-cards, .item-cards {
            display: flex;
            gap: 10px;
            width: 100%;
            margin-bottom: 100px;
        }

        .new-arrivals {
            display: flex;
            align-items: center;
            justify-content: center;
            background-image: url('/banner-3-2x-scaled.jpg');
            min-height: 500px;
            width: 100%;
            background-attachment: fixed;
            background-position:bottom;
            background-repeat: no-repeat;
            background-size: cover;
            margin-bottom: 100px;

            .new-arr-card {
                display: flex;
                align-items: center;
                justify-content: center;
                width: 100%;
                height: 500px;
            }
        }

        .items-section {
            height: 100px;
            margin-bottom: 50px;
        }

        .item-cards {
            gap: 30px;
        }

    }
}


</style>