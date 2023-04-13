<script>


export default {

    name: 'CardItem',

    data() {
        return {

        }
    },

    props: {
        img: String,
        text: String,
        link: String,
        title: String,
        subtitle: String,
        button: String,
        category: String,
        list: Number,
        price: String,
        isJumboCard: Boolean,
        isJumboTitle: Boolean,
        isSectionTitle: Boolean,
        isProducts: Boolean,
        isOnlyProducts: Boolean,
        isFood: Boolean,
        isItemsTitle: Boolean,
        isOnlyItems: Boolean,
        isTestimonials: Boolean,
        isArticles: Boolean,
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
    <!-- card inserita orizzontalmente alla fine del jumbo -->
    <div v-if="isJumboCard == true" class="card-item jumbo-card">
        <div class="jumbo-image">
            <img :src="img" alt="">
        </div>
        <span> {{ text }} </span>
        <a href=""> {{ link }} </a>
    </div>

    <!-- card inserita al centro del jumbo, con il titolo principale -->
    <div v-if="isJumboTitle == true" class="card-item jumbo-title">
        <h3> {{ subtitle }} </h3>
        <h1> {{ title }} </h1>
        <button> {{ button }} </button>
    </div>

    <!-- card dei prodotti singoli, riutilizzata nella sezione categories e items -->
    <div v-if="isProducts == true" class="card-item product-card">
        <img :src="img" alt="">
        <div class="cart-hover" v-if="isOnlyItems == true">
            <div class="cart-hover-container">
                <i class="fa-regular fa-square-check"></i>
            </div>
            <span class="cart-tag"><a href="">View cart</a></span>
        </div>
        <span v-if="isOnlyProducts == true"> {{ category }} ({{ list }})</span>
        <span v-if="isOnlyItems == true"> {{ title }} </span>
        <small v-if="isOnlyItems == true" v-html="price"></small>
    </div>

    <!-- card utilizzata per le tipologie di cibo -->
    <div v-if="isFood == true" class="card-item food-card">
        <h3> {{ title }} </h3>
        <h4> {{ subtitle }} </h4>
        <img :src="img" alt="">
        <button> {{ button }} </button>
    </div>

    <!-- card utilizzata per i new arrivals -->
    <div v-if="isSectionTitle == true" class="card-item section-title">
        <h3> {{ subtitle }} </h3>
        <h2> {{ title }} </h2>
        <button> {{ button }} </button>
    </div>

    <!-- card simile alla precedente, utilizzata prima degli items -->
    <div v-if="isItemsTitle == true" class="card-item items">
        <div class="items-titles">
            <h3> {{ subtitle }} </h3>
            <h2> {{ title }} </h2>
        </div>
        <button> {{ button }} </button>
    </div>

    <!-- card utilizzata per i testimonials -->
    <div v-if="isTestimonials == true" class="card-item testimonials">
        <div class="testimonial-image">
            <img :src="img" alt="">
        </div>
        <p> {{ text }} </p>
        <span> {{ title }} </span>
    </div>

    <!-- card utilizzata nella sezione degli articoli -->
    <div v-if="isArticles == true" class="card-item articles">
        <img :src="img" alt="">
        <div class="article-hover">
                <span class="title"> {{ title }}</span>
                <span class="section">Tips & Tricks</span>
        </div>
        <span> {{ title }} </span>
        <span class="date"> {{ text }} </span>
    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.card-item {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;

    
    &.jumbo-card {
        gap: 40px;
        height: 100%;

        .jumbo-image {
            height: 100%;
            padding-top: 15px;

            img {
                height: 100%;
                object-fit: contain;
                object-position: bottom;
            }
        }
        
    
        a {
            color: rgb(179, 183, 172);
        }
    }
    &.jumbo-title {
        flex-flow: column nowrap;
        align-items: flex-start;
        gap: 50px;
        width: 50%;
        height: 100%;
        color: white;
    
        h1 {
            font-family: 'Times New Roman', Times, serif;
            font-size: 3.5rem;
            font-weight: lighter;
        }
    
        h3 {
            text-transform: uppercase;
        }
    
        button {
            @include button();
            width: 200px;
            font-size: 0.8rem;

            &:hover {
                background-color: $tertiary;
                color: white;
                cursor: pointer;
            }
        }
    }

    &.product-card {
        position: relative;
        flex-flow: column;
        width: calc(100% / 4 - (30px / 4));
        gap: 20px;

        span {
            font-size: 1.1rem;
        }

        small {
            color: $tertiary;
        }

        .cart-hover {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -85%);
            color: white;

            .cart-hover-container {
                display: flex;
                align-items: center;
                justify-content: center;
                width: 60px;
                height: 60px;
                background-color: rgba(0,0,0,0.8);
                border-radius: 50%;
                font-size: 2rem;
            }

            .cart-tag {
                text-transform: uppercase;
                font-size: 0.8rem;
                
                a {
                    text-decoration: none;
                    color: white;

                }
            }
        }

        img {
            width: 100%;
        }

        &:hover .cart-hover {
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            gap: 15px;
        }

        &:hover img {
            filter: contrast(75%) brightness(60%) sepia(80%);
        }
    }

    &.food-card {
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        gap: 10px;
        width: calc(100% / 3 - (10px / 3));
        padding: 40px;
        background-color: $primary;
        @include background-image();
        background-size: 70%;
        background-repeat: repeat-x;

        h3 {
            color: white;
            font-family: serif;
            font-size: 2.5rem;
        }

        h4 {
            color: $tertiary;
            padding-top: 20px;
            font-size: 1.2rem;
        }

        img {
            width: 100%;
            padding: 40px;
        }

        button {
            @include button();
            @include button-tertiary();
            width: 200px;

            &:hover {
                background-color: rgb(42, 84, 42);
                cursor: pointer;

            }
        }

        &:hover {
            transform: scale(1.03);
            background-color: $foodCard;
        }
    }

    &.section-title {
        height: 100%;
        flex-flow: column nowrap;
        gap: 40px;
        color: white;

        h3 {
            text-transform: uppercase;
            font-size: 0.9rem;
            text-shadow: 2px 2px black;
        }

        h2 {
            font-family: serif;
            font-size: 4rem;
            text-shadow: 2px 2px black;
        }

        button {
            @include button();
            width: 200px;
            font-size: 0.8rem;

            &:hover {
                background-color: $tertiary;
                color: white;
                cursor: pointer;
            }

        }
    }

    &.items {
        justify-content: space-between;
        height: 100%;

        .items-titles {
            display: flex;
            flex-flow: column;
            gap: 20px;
        }

        h3 {
            color: $tertiary;
        }

        h2 {
            font-family: serif;
            font-size: 2.5rem;
            font-weight: lighter;
        }

        button {
            @include button();
            @include button-tertiary();
            width: 200px;
            font-size: 0.9rem;

            &:hover {
                background-color: rgb(42, 84, 42);
                cursor: pointer;
            }
        }

    }

    &.testimonials {
        display: flex;
        flex-flow: column;
        align-items: center;
        gap: 20px;
        width: calc(100% / 3 );
        padding: 10px;
        
        .testimonial-image {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            overflow: hidden;

            img {
                width: 100%;
                object-fit: contain;
            }

        }

        p {
            text-align: center;
            line-height: 1.5rem;
            color: white;
        }
    
        span {
            color: rgb(156, 165, 157);
        }
    }

    &.articles {
        position: relative;
        display: flex;
        flex-flow: column nowrap;
        align-items: flex-start;
        width: calc(100% / 4 - (30px / 4));
        gap: 20px;

        img {
            width: 100%;
        }

        .article-hover {
            position: absolute;
            display: none;
            width: 100%;
            height: 100%;
            color: white;
            text-align: center;
            
            .title {
                position: absolute;
                top: 30%;
                left: 0;
                width: 100%;
                font-size: 1.2rem;
                padding: 0 20px;
            }

            .section {
                position: absolute;
                top: 50%;
                left: 0;
                width: 100%;
                font-size: 0.8rem;
            }
            
        }

        .date {
            font-size: 0.8rem;
        }

        &:hover .article-hover {
            display: inline-block
            
        }


        &:hover img {
            filter: contrast(75%) brightness(60%) sepia(80%);
        }
    }

}

</style>