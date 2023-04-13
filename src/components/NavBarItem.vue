<script>


export default {

    name: 'NavBarItem',

    data() {
        return {
            isActive: false,
        }
    },

    props: {
        singleLink: String,
        singleIcon: String,
        jumboLink: Object,
        isLink: Boolean,
        isIcon: Boolean,
        isHeader: Boolean,
        dropDown: Boolean,
        isJumbo: Boolean,
        isMain: Boolean,
    },

    methods: {
        changeActive() {
            this.isActive = true;
        }
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
    <!-- lista di link, riutilizzata nell'header e nel footer -->
    <div @click="changeActive()" :class="isActive == true ? 'active' : ''" class="nav-link" v-if="isLink == true" :isActive="false"> {{ singleLink }} <i class="fa-solid fa-angle-down" v-if="dropDown == true"></i></div>
    
    <!-- lista di icone nel footer -->
    <i :class="`fa-brands ${singleIcon}`" v-if="isIcon == true"></i>
    
    <!-- lista di icone nell'header -->
    <i :class="`fa-solid ${singleIcon}`" v-if="isHeader == true"></i>

    <!-- lista superiore nel jumbo, con i link inseriti come tag HTML nell'array -->
    <div class="jumbo-nav" v-if="isJumbo == true">
        <i :class="`fa-solid ${jumboLink.icon}`"></i>
        <span v-html="jumboLink.text"></span>
    </div>

    <!-- lista di icone in fondo alla main section -->
    <div class="main-nav" v-if="isMain == true">
        <i :class="`fa-solid ${jumboLink.icon}`"></i>
        <span v-html="jumboLink.text"></span>
    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.nav-link {
    display: flex;
    align-items: center;
    gap: 5px;
    color: $linkColor;
    font-weight: bold;

    &:hover {
        color: black;
        cursor: pointer;
    }
}

.active {
    color: black;

}
.jumbo-nav {
    display: flex;
    align-items: center;
    gap: 10px;

    
}

.main-nav {
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
    color: white;

    i {
        font-size: 1.8rem;
    }

    span {
        font-size: 0.8rem;
    }
}


</style>