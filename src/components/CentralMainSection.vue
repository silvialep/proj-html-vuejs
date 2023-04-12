<script>

import CardItem from './CardItem.vue';
import NavBarItem from './NavBarItem.vue';

export default {

    name: 'CentralMainSection',

    data() {
        return {
            testimonials: [
                {
                    img: '/avatar-3.jpg',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem voluptatibus a officia nam dolor dicta cupiditate cum earum in.',
                    title: 'Lisa Smith, ThemeFusion',
                },
                {
                    img: '/avatar-1.jpg',
                    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aut necessitatibus, ipsum, ullam debitis unde saepe accusantium fugiat excepturi aspernatur',
                    title: 'Melissa Green, ThemeFusion',
                },
                {
                    img: '/avatar-4.jpg',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia, repudiandae? Iste unde, sed reprehenderit illo asperiores ad aliquam consequuntur aut a.',
                    title: 'Sam Lewis, ThemeFusion',
                },
            ],
        }
    },

    props: {

    },

    emits: ['',

    ],

    components: {
        CardItem,
        NavBarItem,
    },


    computed: {
        proprieta() {
        }
    },



}


</script>

<template>
    <div id="testimonials-section">
        <div id="testimonials-container">
            <h3>Users Testimonials</h3>
            <div id="testimonials-cards">
                <CardItem v-for="testimonial in testimonials" :img="testimonial.img" :text="testimonial.description" :title="testimonial.title" :isTestimonials="true"></CardItem>
            </div>
        </div>
    </div>
    <div id="newsletter-section">
        <div id="newsletter-container">

        </div>
    </div>


</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

#testimonials-section {
    @include background-image();

    background-repeat: repeat-x;
    background-size: 15%;
    min-height: 500px;
    background-color: $primary;

    #testimonials-container {
        @include container();
        flex-flow: column nowrap;
        align-items: center;
        gap: 50px;
        padding: 100px 0;

        h3 {
            color: white;
            font-family: serif;
            font-size: 2.5rem;
        }

        #testimonials-cards {
            display: flex;
            justify-content: space-between;
            gap: 40px;
            width: 100%;
        }
    }

    
}

#newsletter-section {
    min-height: 1000px;
    background-color: white;

    #newsletter-container {
        @include container();
        min-height: 500px;
        background-image: url('/banner-7-2x-scaled.jpg');
    }
}



</style>