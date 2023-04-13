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

            articles: [
                {
                    image: '/blog-1.jpg',
                    title: 'How to \'loose leash walk\' your dog',
                    date: 'April 21st, 2020',
                },
                {
                    image: '/blog-2.jpg',
                    title: 'Stop cats from scratching furniture',
                    date: 'April 19th, 2020',
                },
                {
                    image: '/blog-3.jpg',
                    title: 'Where to buy the best pet food',
                    date: 'April 18th, 2020',
                },
                {
                    image: '/blog-4.jpg',
                    title: 'Proper care for your pet toys',
                    date: 'April 17th, 2020',
                },
            ],
        }
    },

    props: {

    },

    emits: [

    ],

    components: {
        CardItem,
        NavBarItem,
    },


    computed: {

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
            <div id="newsletter">
                <h3>Join our newsletter</h3>
                <p>Nemo est repellat perspiciatis? Vel, dolore atque? Maiores, facere eos! Assumenda, iusto sed?</p>
                <div class="newsletter-form">
                    <input type="text" placeholder="Insert your email ...*">
                    <button>Subscribe</button>
                </div>
            </div>
        </div>
    </div>
    <div id="tips-tricks">
        <div class="title">
            <h3>Get the best tips & tricks</h3>
            <span>Recent articles</span>
        </div>
        <div id="articles-section">
            <CardItem v-for="article in articles" :img="article.image" :title="article.title" :text="article.date" :isArticles="true"></CardItem>
        </div>
        <button>Read all articles</button>
        

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
        padding: 100px 0 200px;

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
    background-color: white;
    
    #newsletter-container {
        @include container();
        position: relative;
        min-height: 400px;
        
        #newsletter {
            display: flex;
            flex-flow: column;
            gap: 40px;
            width: 100%;
            height: 100%;
            position: absolute;
            top: -100px;
            background-image: url('./banner-7-2x-scaled.jpg');
            background-size: cover;
            padding: 100px;

            h3 {
                font-family: serif;
                font-size: 2.5rem;
            }

            p {
                line-height: 1.5rem;
                width: 50%;
            }

            .newsletter-form {
                display: flex;
                gap: 20px;
                padding: 20px 0;

                input {
                    width: 350px;
                    outline: none;
                    border: none;
                    padding: 20px;
                    border-radius: 30px;
                    background-color: rgb(248, 245, 242);
                }

                button {
                    @include button();
                    @include button-tertiary();
                    width: 200px;

                    &:hover {
                    background-color: rgb(42, 84, 42);
                    cursor: pointer;
            }
                }
            }

        }
    }
}

#tips-tricks {
    @include container();
    flex-flow: column;
    align-items: center;

    .title {
        display: flex;
        flex-flow: column;
        align-items: center;
        justify-content: center;
        gap: 30px;
        margin-bottom: 50px;

        h3 {
            font-size: 2rem;
            font-family: serif;
        }

        span {
            color: $tertiary;
        }
    }

    #articles-section {
        display: flex;
        gap: 30px;
        margin-bottom: 50px;
    }

    button {
        @include button();
        @include button-tertiary();
        width: 200px;
        margin-bottom: 100px;

        &:hover {
            background-color: rgb(42, 84, 42);
            cursor: pointer;
        }
    }
}


</style>