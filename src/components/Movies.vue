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

    function addMovie(movie) {
        movie.grade = parseInt(movie.grade);       
        movies.value.push(movie);
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
            <Movie v-for="movie in movies" 
            :title="movie.title"
            :grade="movie.grade" />
        </ul>
    </div>
        
</template>

<style>
ul {
    padding: 0 !important;
    margin: 0 !important;
}

</style>
