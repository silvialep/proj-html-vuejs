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
        isJumboCard: Boolean,
        isJumboTitle: Boolean,
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

}
.jumbo-title {
    display: flex;
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

</style>