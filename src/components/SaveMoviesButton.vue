<script setup>
    const emit = defineEmits(['pass-movie-event'])

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
            let obj = {title: title.value, grade: grade.value};
            emit("pass-movie-event", obj)
        }
        
    }
</script>

<template>
    <input id="submit" type="submit" name="submit-button" @click="submitMovie" class="btn btn-success">
</template>

<style scoped>
#submit {
    margin: 4px 0 2px 0 !important;
}
</style>
