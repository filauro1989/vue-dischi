<template>
        <div class="container-fluid bg-color" >
            <select @change="getValue()" name="genreSelect" id="genreSelect">
              <option value="all">All</option>
              <option value="rock">Rock</option>
              <option value="pop">Pop</option>
              <option value="jazz">Jazz</option>
              <option value="metal">Metal</option>
            </select>
            <div v-if="filteredCards" class="w-60 centered pt-6">
                <div class="row row-cols-5">
                    <!-- <div class="col text-center text-light px-3">
                        <div class="card-wrapper card-bg-color p-3">
                            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
                            <h4>NEW JERSEY</h4>
                            <h5>Bon Jovi</h5>
                            <h6>1988</h6>
                        </div>
                    </div> -->
                    <Cards v-for="(card, index) in filteredCards" :key="index" :image="card.poster" :title="card.title" :author="card.author" :year="card.year" :genre="card.genre">
                    </Cards>
                </div>
            </div>
            <div class="w-60 centered pt-6" v-else>
                <h1 class="loading text-light">Loading</h1>
                <div class="lds-spinner"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>
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
            filteredCards: null,
            selectedValue: '',
            queryApi: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    computed: {
      getSelect() {
        // this.filteredCards = this.cards;
        if (this.selectedValue === 'all') {
          console.log(this.selectedValue);
          return this.filteredCards;
        }
        return this.filteredCards.filter((element) => element.genre.toLowerCase().includes(this.selectedValue.toLowerCase()));       
      }
    },
    created() {
      },
    mounted() {
      setTimeout(() => {
        this.getCard();
        }, 1000);
    
    },
    methods: {
      getCard() {
        axios.get(this.queryApi)
        .then((result) => {
          this.cards = result.data.response;
          this.filteredCards = result.data.response;
        })
        .catch((error) => {
            console.log(error);
        });
      },
      // getSelect() {
      //   this.selectedValue = document.getElementById('genreSelect').value;
      //   this.filteredCards = this.cards;
      //   if (this.selectedValue === 'all') {
      //     return this.filteredCards;
      //   } else {
      //     this.filteredCards = this.filteredCards.filter((element) => element.genre.toLowerCase().includes(this.selectedValue.toLowerCase()));
      //   }
      //   return this.filteredCards;
      
      // }
      getValue() {
        this.selectedValue = document.getElementById('genreSelect').value;
      },

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
    .lds-spinner {
  color: official;
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-spinner div {
  transform-origin: 40px 40px;
  animation: lds-spinner 1.2s linear infinite;
}
.lds-spinner div:after {
  content: " ";
  display: block;
  position: absolute;
  top: 3px;
  left: 37px;
  width: 6px;
  height: 18px;
  border-radius: 20%;
  background: #fff;
}
.lds-spinner div:nth-child(1) {
  transform: rotate(0deg);
  animation-delay: -1.1s;
}
.lds-spinner div:nth-child(2) {
  transform: rotate(30deg);
  animation-delay: -1s;
}
.lds-spinner div:nth-child(3) {
  transform: rotate(60deg);
  animation-delay: -0.9s;
}
.lds-spinner div:nth-child(4) {
  transform: rotate(90deg);
  animation-delay: -0.8s;
}
.lds-spinner div:nth-child(5) {
  transform: rotate(120deg);
  animation-delay: -0.7s;
}
.lds-spinner div:nth-child(6) {
  transform: rotate(150deg);
  animation-delay: -0.6s;
}
.lds-spinner div:nth-child(7) {
  transform: rotate(180deg);
  animation-delay: -0.5s;
}
.lds-spinner div:nth-child(8) {
  transform: rotate(210deg);
  animation-delay: -0.4s;
}
.lds-spinner div:nth-child(9) {
  transform: rotate(240deg);
  animation-delay: -0.3s;
}
.lds-spinner div:nth-child(10) {
  transform: rotate(270deg);
  animation-delay: -0.2s;
}
.lds-spinner div:nth-child(11) {
  transform: rotate(300deg);
  animation-delay: -0.1s;
}
.lds-spinner div:nth-child(12) {
  transform: rotate(330deg);
  animation-delay: 0s;
}
@keyframes lds-spinner {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

</style>