<script setup>
    import AddMovieForm from './AddMovieForm.vue'
    import Movies from './Movies.vue'
    import {reactive, ref} from 'vue'
    const counter = reactive ({count:69})
</script>

<template>
    <div>
        <AddMovieForm />
        <Movies />
    </div>
</template>
