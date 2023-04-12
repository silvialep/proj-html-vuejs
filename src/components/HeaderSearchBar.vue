<script>

import NavBarItem from './NavBarItem.vue';

export default {

    name: 'HeaderSearchBar',

    data() {
        return {
            numberCall: '1.800.555.2368',
            headerIcons: [
                'fa-bag-shopping',
                'fa-user',
            ],

        }
    },

    props: {
    },

    emits: [

    ],

    components: {
        NavBarItem,
    },


    computed: {
    },



}


</script>

<template>
    <nav>
        <div class="logo">
            <img src="/dark-pet-logo.png" alt="Avada logo">
        </div>
        <div class="search-bar">
            <i class="fa-solid fa-magnifying-glass"></i>
            <input type="text" placeholder="Search...">
        </div>
        <div class="questions">
            <span><strong>Questions?</strong> Call us: {{ numberCall }}</span>

        </div>
        <div class="nav-icons">
            <NavBarItem v-for="singleIcon in headerIcons" :singleIcon="singleIcon" :isHeader="true"></NavBarItem>
        </div>

    </nav>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

nav {
    @include container();
    justify-content: space-between;
    height: 60px;
    padding: 10px;
    font-size: 0.9rem;

    .logo {
        display: flex;
        align-items: center;
        gap: 10px;
        height: 100%;
        
        img {
            height: 100%;
        }

        strong {
            font-size: 1.3rem;
        }
    }

    .search-bar {
        display: flex;
        align-items: center;
        width: 300px;
        background-color: rgb(243, 244, 243);
        border-radius: 20px;
        padding: 10px;
        font-size: 0.8rem;

        input {
            width: 100%;
            padding: 10px;
            border: none;
            background-color: rgb(243, 244, 243);
            font-size: 0.8rem;
            outline: none;

        }
    }

    .questions {
        display: flex;
        align-items: center;
    }

    .nav-icons {
        display: flex;
        align-items: center;
        gap: 15px;
        font-size: 1rem;
    }
}

</style>