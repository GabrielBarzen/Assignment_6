<script setup>
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
        }
        
    }
</script>

<template>
    <input type="submit" name="submit-button" @click="submitMovie" class="btn btn-success">
</template>

<style scoped>
</style>
