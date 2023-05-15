<script setup>
    import AddMovieForm from './AddMovieForm.vue'
    import OrderByAlphaButton from './OrderByAlphaButton.vue'
    import OrderByGradeButton from './OrderByGradeButton.vue'
    import Movie from './Movie.vue'
    import { ref } from 'vue'

    function addMovie(movie) {
        let gradeStr = "";
        for (let i = 0; i < movie.grade; i++) {
            gradeStr += "*";
        }
        movie.grade = gradeStr;
        
        movies.value.push(movie);
    }

    let movies = ref([
        {
            title: 'dogs 2',
            grade: "*****"
        },
        {
            title: 'cat attack',
            grade: "**"
        },
        {
            title: 'horse movie',
            grade: "***"
        }
    ]);

</script>

<template>
    <AddMovieForm @add-movie-event="addMovie" />
    <div>
        <OrderByAlphaButton />
        <OrderByGradeButton />
    </div>
    <div>
        <ul>
            <Movie v-for="movie in movies" 
            :title="movie.title"
            :grade="movie.grade" />
        </ul>
    </div>
        
</template>
