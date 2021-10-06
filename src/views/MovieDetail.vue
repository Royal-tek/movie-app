<template>
    <div class="movie-detail">
        <p class="title">{{movie.Title}}</p>
        <p class="year">{{movie.Year}}</p>
        <img :src="movie.Poster" alt="Movie poster" class="featured-image">
    
        <p class="plot">Plot: {{movie.Plot}}</p>
        <p class="actor"><big><span>Actors:</span></big> {{movie.Actors}}</p>
        <p class="date">Release date: {{movie.Released}}</p>
        <p class="writer">Writer: {{movie.Writer }}</p>
        <!-- {{movie.Ratings}} -->
        </div>
</template>

<script>
import axios from 'axios'
import { ref, onBeforeMount } from 'vue'
import { useRoute } from 'vue-router'
export default {
    setup(){
        const movie = ref({});
        const route = useRoute()

        onBeforeMount(()=>{
            axios.get(`http://www.omdbapi.com/?apikey=39747de2&i=${route.params.id}&plot=full`)
            .then(response=>{
                movie.value = response.data
                console.log(movie.value)
            })
        });

        return {
            movie
        }
    }
}
</script>

<style lang="scss">

.movie-detail{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    .title{
        color: #fff;
        text-align: center;
        margin: 30px 0 10px;
        font-size: 30px;
        text-transform: uppercase;
    }
    .year{
        color: #42bb83;
        font-style: italic;
        text-align: center;
        font-size: 20px;
        margin: 10px 0 ;
    }
    .plot{
        color: #fff;
        font-size: 18px;
        font-family: sans-serif;
        max-width: 80%;
        margin: 20px 0;
        background-color: #496583;
        padding: 30px;
        // flex: 1 1 100%;
        border-radius: 0px 0px 15px 15px;
        // display: block;
    }
    .actor{
        color: #42bb83;
        font-size: 19px;
        margin: 10px 0;
    }
    .date{
        color: #fff;
        margin: 10px 0;
    }
    .writer{
        color: #42bb83;
        margin: 10px 0;
    }
}
</style>