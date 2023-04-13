<script>

import AppJumbo from './AppJumbo.vue';
import TopMainSection from './TopMainSection.vue';
import CentralMainSection from './CentralMainSection.vue';
import BottomMainSection from './BottomMainSection.vue';

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
        BottomMainSection,
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

        <BottomMainSection></BottomMainSection>
        
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.main-container {
    // height: 200px;
    background-color: white;
}

</style>