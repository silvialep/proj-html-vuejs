<script>

import NavBarItem from "./NavBarItem.vue";

export default {

    name: 'AppFooter',

    data() {
        return {
            numberCall: '1.800.555.2368',
            address: '1234 Avada Avenue Avadaville',
            compMail: 'info@avada-company.com',

            brandLinks:
                {
                    title: 'Shop by brand',
                    links: ['Bed', 'Food', 'Toys', 'Transport'],
                },

            usefulLinks:
                {
                    title: 'Useful links',
                    links: ['My account', 'Orders', 'Checkout', 'Cart'],
                },
            
            footerLinks: 
                [
                    'Home', 'About', 'Blog', 'Contact', 'Shop'
                ],

            footerIcons: 
                [
                    'fa-facebook-f',
                    'fa-twitter',
                    'fa-instagram',
                    'fa-youtube',
                ],
            
            footerCredits: 
                [
                    'Copyright 2012 - 2020',
                    ' | ',
                    'Avada Theme by ThemeFusion',
                    ' | ',
                    'All Rights Reserved',
                    ' | ',
                    'Powered by Wordpress',
                ]

        }
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
    <footer>
        <div id="footer-up">
            <div class="footer-list">
                <img src="/mobile-light-pet-logo-2x.png" alt="Avada logo">
                <p>
                    {{ address }}
                    <br>
                    {{ compMail }}
                    <br>
                    Call us: {{ numberCall }}
                </p>
            </div>
            <div class="footer-list">
                <ul>
                    <li class="links-title"> {{ brandLinks.title }} </li>
                    <li v-for="link in brandLinks.links"> {{ link }} </li>
                </ul>
            </div>
            <div class="footer-list">
                <ul>
                    <li class="links-title"> {{ usefulLinks.title }} </li>
                    <li v-for="link in usefulLinks.links"> {{ link }} </li>
                </ul>
            </div>
            <div class="footer-list newsletter">
                <span class="links-title">
                    Subscribe to our newsletter
                </span>
                <input type="text" placeholder="Insert your email...*">
                <button>Subscribe</button>
            </div>

        </div>
        <hr>
        <div class="footer-nav-bar">
            <div class="single-nav top-nav">
                <NavBarItem v-for="singleLink in footerLinks" :singleLink="singleLink" :isLink="true"></NavBarItem>
            </div>
            <div class="single-nav">
                <NavBarItem v-for="singleIcon in footerIcons" :singleIcon="singleIcon" :isIcon="true"></NavBarItem>
            </div>
        </div>
        
        
        
    </footer>
    <div id="footer-black-bar">
        <i class="fa-regular fa-copyright"></i>
        <NavBarItem v-for="singleLink in footerCredits" :singleLink="singleLink" :isLink="true"></NavBarItem>
    </div>
</template>

<style lang="scss" scoped>

@use "../scss/_variables.scss" as *;

footer {
    @include container();
    flex-flow: column nowrap;
    color: white;
    
    #footer-up {
        @include container();
    
        gap: 30px;
        padding: 80px 0;
        font-size: 0.9rem;
        
        .footer-list {
            display: flex;
            justify-content: flex-start;
            // align-items: center;
            flex-flow: column nowrap;
            gap: 10px;
            width: calc(100% / 4);
            padding-bottom: 20px;
    
            img {
                width: 80%;
                margin-bottom: 30px;
                padding-top: 15px;
            }
    
            p {
                line-height: 1.5rem;
            }
    
            ul {
                list-style-type: none;
                font-size: 1rem;
                padding-top: 15px;
    
                li {
                    line-height: 2.6rem;
                    font-size: 0.9rem;
                }
    
            }
            .links-title {
                margin-bottom: 30px;
                font-size: 1.2rem;
                line-height: 1rem;
            }
            
        }
        .newsletter {
            height: auto;
            background-color: rgb(38, 66, 41);
            border-radius: 10px;
            padding: 30px;
            @include background-image();
    
            .links-title {
                line-height: 1.8rem;
                margin-bottom: 20px;
            }
    
            input {
                padding: 15px;
                background-color: white;
                border: none;
                border-radius: 60px;
                margin-bottom: 20px;
                outline: none;
            }
    
            button {
                @include button();
                @include button-tertiary();
            }
        }
    }

    hr {
        color: rgb(53, 70, 55);
    }

    .footer-nav-bar {
        display: flex;
        flex-flow: column;
        gap: 30px;
        padding: 60px 0 100px;

        
        .single-nav {
            display: flex;
            flex-flow: row;
            justify-content: center;
            align-items: center;
            gap: 15px;

        }
        .top-nav {
            gap: 30px;
            color: rgb(169, 170, 165);
        }
    }

}

#footer-black-bar {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5px;
    height: 80px;
    background-color: rgb(0, 0, 0);
    color: white;
    font-size: 0.8rem;

    i {
        font-size: 0.6rem;
    }
}

</style>