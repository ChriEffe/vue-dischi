<template>
<div class="container-fluid bg">
    <div class="container-70">
        <div class="row row-cols-6 pt-5 pb-5" v-if="cards">
            <Card v-for="(card, index) in cards" :key="index" :poster="card.poster" :poster-alt="card.title" :title="card.title" :author="card.author" :year="card.year"/>
        </div>
    </div>
</div>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
export default {
name: 'Main',
components: {
    Card,
},
data(){
    return{
        cardsApi: 'https://flynn.boolean.careers/exercises/api/array/music',
        cards: null,
    };
},
created() {
        axios
        .get(this.cardsApi)
        .then((result) => {
        console.log(result.data.response);
        this.cards = result.data.response;
        })
        .catch((error) => {
        console.log(error);
        })
    },
}
</script>

<style lang="scss">
*{
    border: 0;
    margin: 0;
    box-sizing: border-box;
}
.bg{
    background-color: #1e2d3b;
    height: 100%;
    display: flex;
    align-items: center;
    .container-70{
        width: 70%;
        margin: 0 auto;
        .flex{
            display: flex;
            flex-direction: column;
            justify-content: start;
            align-items: center;
        }
        .col{
            background-color: #2e3a46;
            img{
            width: 100%;
            }
        }
    }
}
h1{
    color: white;
    text-transform: uppercase;
    text-align: center;
}
h2{
    font-size: 1.2em;
    color: white;
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 0.5em;
}
h3, h4{
    color: #808080;
    text-align: center;
    font-size: 0.7em;
}
</style>