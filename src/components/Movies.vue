<script setup>
    import OrderByAlphaButton from './OrderByAlphaButton.vue'
    import OrderByGradeButton from './OrderByGradeButton.vue'
    import Movie from './Movie.vue'
    import { ref } from 'vue'
  
    const movies = ref([
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
