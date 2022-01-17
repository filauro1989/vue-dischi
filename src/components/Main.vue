<template>
        <div class="container-fluid bg-color" >
            <div class="w-60 centered pt-6">
                <div class="row row-cols-5">
                    <!-- <div class="col text-center text-light px-3">
                        <div class="card-wrapper card-bg-color p-3">
                            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
                            <h4>NEW JERSEY</h4>
                            <h5>Bon Jovi</h5>
                            <h6>1988</h6>
                        </div>
                    </div> -->
                    <Cards v-for="(card, index) in cards" :key="index +card.id" :image="card.poster" :title="card.title" :author="card.author" :year="card.year">
                    </Cards>
                </div>
            </div>
        </div>
</template>

<script>

import axios from 'axios';
import Cards from './Cards.vue'

export default {
    name: 'Main',
    components: {
        Cards,
    },
    data() {
        return {
            cards: null,
        }
    },
    created() {
    this.getCard();
    },
    mounted() {
    
    },
    methods: {
    getCard() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result) => {
        this.cards = result.data.response;
        }).catch((error) => {
            console.log(error);
        });
    }
    }
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss"; 
    @import "../assets/scss/partials/_commons.scss"; 

    .bg-color {
        background-color: $backgroundColor;
            
    };
    .container-fluid {
        height: calc(100vh - 50px - 1.4em);
        width: 100vw;
    };

</style>