<script setup>
    import AddMovieForm from './AddMovieForm.vue'
    import OrderByAlphaButton from './OrderByAlphaButton.vue'
    import OrderByGradeButton from './OrderByGradeButton.vue'
    import Movie from './Movie.vue'
    import { ref } from 'vue'

    function orderGrade() {
        movies.value.sort((a, b) => {
            return b.grade-a.grade;
        })
    }

    function orderAlpha() {
        console.log("DOOGGG")
        movies.value.sort((a, b) => {
            return ('' + a.title).localeCompare(b.title);
        })
    }

    function addMovie(movie) {
        // let gradeStr = "";
        // for (let i = 0; i < movie.grade; i++) {
        //     gradeStr += "*";
        // }
        // movie.grade = gradeStr;
        
        movies.value.push(movie);
    }

    let movies = ref([
        {
            title: 'dogs 2',
            grade: 5
        },
        {
            title: 'cat attack',
            grade: 2
        },
        {
            title: 'horse movie',
            grade: 3
        }
    ]);

</script>

<template>
    <AddMovieForm @add-movie-event="addMovie" />
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
