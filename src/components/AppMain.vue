<script>

import AppJumbo from './AppJumbo.vue';
import TopMainSection from './TopMainSection.vue';
import CentralMainSection from './CentralMainSection.vue';

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
        CentralMainSection,
    },


    computed: {
    },



}


</script>

<template>
    <div class="main-container">

        <AppJumbo></AppJumbo>

        <TopMainSection ></TopMainSection>
        
        <CentralMainSection></CentralMainSection>

    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.main-container {
    // height: 200px;
    background-color: white;
}

</style>