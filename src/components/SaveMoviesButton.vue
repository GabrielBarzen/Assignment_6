
<script setup>
    import Movie from './Movie.vue'
    import { h } from 'vue'
    function submitMovie(e) {
        e.preventDefault();

        const title = document.querySelector("#title-input");
        const grade = document.querySelector("#grade-input");

        let valid = true;

        if(title.value == "") {
            alert("Please enter title")
            valid = false;
        }
        if(grade.value == "") {
            alert("Please enter grade")
            valid = false;
        }

        if (valid) {
            new Vue
            console.log(Movie)
            let mp = Movie;
            mp.props = { 'title' : title.value, 'grade' : grade.value};
            let ml = document.querySelector("#movie-list")
            
            ml.append(mp.render._sfc_render())
            

        }        
    }
</script>

<template>
    <input type="submit" name="submit-button" @click="submitMovie" class="btn btn-success">
</template>

<style scoped>
</style>
