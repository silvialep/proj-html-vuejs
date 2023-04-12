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
        isJumboCard: Boolean,
        isJumboTitle: Boolean,
        isProducts: Boolean,
        isFood: Boolean,
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
        <span> {{ category }} ({{ list }})</span>
    </div>

    <div v-if="isFood == true" class="card-item food-card">
        <h3> {{ title }} </h3>
        <h4> {{ subtitle }} </h4>
        <img :src="img" alt="">
        <button> {{ button }} </button>

    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.card-item {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;

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
        padding: 60px 30px;
        background-color: $secondary;
        @include background-image();
        background-size: 60%;
        background-repeat: repeat-x;

        h3 {
            color: white;
            font-family: serif;
            font-size: 2rem;
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

}

</style>