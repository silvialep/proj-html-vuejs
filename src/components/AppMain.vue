<script>

import AppJumbo from './AppJumbo.vue';
import TopMainSection from './TopMainSection.vue';

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
        TopMainSection,
    },


    computed: {
    },



}


</script>

<template>
    <div id="main-container">

        <AppJumbo></AppJumbo>

        <TopMainSection></TopMainSection>
        
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#main-container {
    // height: 200px;
    background-color: white;
}

</style>