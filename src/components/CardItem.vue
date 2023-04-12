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
    <div v-if="isJumboCard == true" class="card-item">
        <img :src="img" alt="">
        <span> {{ text }} </span>
        <a href=""> {{ link }} </a>
    </div>

    <div v-if="isJumboTitle == true" class="card-item jumbo-title">
        <h3> {{ subtitle }} </h3>
        <h1> {{ title }} </h1>
        <button> {{ button }} </button>
    </div>

    <div v-if="isProducts == true" class="card-item product-card">
        <img :src="img" alt="">
        <span v-if="isOnlyProducts == true"> {{ category }} ({{ list }})</span>
        <span v-if="isOnlyItems == true"> {{ title }} </span>
        <small v-if="isOnlyItems == true" v-html="price"></small>
    </div>

    <div v-if="isFood == true" class="card-item food-card">
        <h3> {{ title }} </h3>
        <h4> {{ subtitle }} </h4>
        <img :src="img" alt="">
        <button> {{ button }} </button>
    </div>
    <div v-if="isSectionTitle == true" class="card-item section-title">
        <h3> {{ subtitle }} </h3>
        <h2> {{ title }} </h2>
        <button> {{ button }} </button>
    </div>
    <div v-if="isItemsTitle == true" class="card-item items">
        <div class="items-titles">
            <h3> {{ subtitle }} </h3>
            <h2> {{ title }} </h2>
        </div>
        <button> {{ button }} </button>
    </div>
    
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.card-item {
    display: flex;
    justify-content: center;
    align-items: center;

    img {
        height: 90%;
        object-position: bottom;
    }

    a {
        color: rgb(179, 183, 172);
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
        }
    }

    &.product-card {
        flex-flow: column;
        width: calc(100% / 4 - (30px / 4));
        gap: 20px;

        span {
            font-size: 1.1rem;
        }

        small {
            color: $tertiary;
        }

        img {
            width: 100%;
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
        }
    }

}

</style>