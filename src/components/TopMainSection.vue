<script>
import CardItem from './CardItem.vue';



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
        }
    },

    props: {

    },

    emits: [

    ],

    components: {
    CardItem
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
                <CardItem v-for="product in productsCategories" :list="product.img.length" :category="product.category" :img="product.img[indice]" :isProducts="true"></CardItem>
            </div>
            <div class="foods-cards">
                <CardItem v-for="food in foods" :isFood="true" :title="food.title" :subtitle="food.description" :img="food.image" :button="food.button" ></CardItem>
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

            }

            p {
                line-height: 2rem;
                text-align: center;
            }
        }

        .products-cards, .foods-cards {
            display: flex;
            gap: 10px;
            width: 100%;
            margin-bottom: 100px;
        }

    }
}


</style>