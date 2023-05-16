<script setup>
    import AddMovieForm from './AddMovieForm.vue'
    import OrderByAlphaButton from './OrderByAlphaButton.vue'
    import OrderByGradeButton from './OrderByGradeButton.vue'
    import Movie from './Movie.vue'
    import { ref } from 'vue'

    function orderGrade() {
        movies.value.sort((a, b) => {
            console.log(movies)
            return b.grade-a.grade;
        })

    }

    function orderAlpha() {
        movies.value.sort((a, b) => {
            console.log(movies)
            return ('' + a.title).localeCompare(b.title);
        })
    }
    let id = 0;
    function addMovie(movie) {
        movie.grade = parseInt(movie.grade);       
        movie.id = id++;
        movies.value.push(movie);
        console.log(movies.value)
    }

    function removeMovie(movie) {
        movies.value = movies.value.filter(o => {
            return o.id != movie.id;
        })
    }

    let movies = ref([]);

</script>

<template>
    <AddMovieForm @add-movie-event="addMovie"/>
    <div>
        <OrderByAlphaButton @order-alpha="orderAlpha"/>
        <OrderByGradeButton @order-grade="orderGrade"/>
    </div>
    <div>
        <ul>
            <Movie  v-for="movie in movies" 
            :title="movie.title"
            :grade="movie.grade"
            :movie-id="movie.id"
            @movie-remove="removeMovie(movie)"/>
        </ul>
    </div>
        
</template>

<style>
ul {
    padding: 0 !important;
    margin: 0 !important;
}

</style>
