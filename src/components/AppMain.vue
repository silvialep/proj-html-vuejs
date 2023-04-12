<script>

import AppJumbo from './AppJumbo.vue';

export default {

    name: 'AppMain',

    data() {
        return {

        }
    },

    emits: [

    ],

    components: {
        AppJumbo,
    },


    computed: {
    },



}


</script>

<template>
    <div id="main-container">
        <AppJumbo></AppJumbo>
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#main-container {
    // height: 200px;
    background-color: white;
}

</style>