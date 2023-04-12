<script>


export default {

    name: 'TopMainSection',

    data() {
        return {

        }
    },

    props: {

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
    <div class="section-container">
        <div id="categories">
            <div id="section-title">
                
            </div>

        </div>

    </div>

</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

.section-container {
    height: 400px;
    background-color: white;

    #categories {
        @include container();


    }
}


</style>