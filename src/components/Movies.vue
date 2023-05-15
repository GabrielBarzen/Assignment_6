<script setup>
    import OrderByAlphaButton from './OrderByAlphaButton.vue'
    import OrderByGradeButton from './OrderByGradeButton.vue'
    import Movie from './Movie.vue'
</script>

<template>
    <div>
        <OrderByAlphaButton />
        <OrderByGradeButton />
    </div>
    <div>
        <ul id="movie-list">
            <Movie />
            <Movie />
            <Movie />
            <Movie />
            <Movie />
            <Movie />
            <Movie />
            <Movie />
        </ul>
    </div>
        
</template>
