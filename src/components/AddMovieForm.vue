
<script setup>
    import SaveMoviesButton from './SaveMoviesButton.vue'

    const emit = defineEmits(['add-movie-event'])

    function passMovie(obj) {
        let title = document.querySelector("#title-input");
        let grade = document.querySelector("#grade-input");
        title.value = "";
        grade.value = "";

        emit("add-movie-event", obj);
    }

</script>

<template>
    <div>
        <form action="post">
            <label for="title">Title:</label>
            <input type="text" class="input-group-text" name="title" id="title-input">
            <label for="grade">Grade:</label>
            <select class="input-group custom-select" name="grade" id="grade-input">
                <option selected value="">Choose grade</option>
                <option value=1>1</option>
                <option value=2>2</option>
                <option value=3>3</option>
                <option value=4>4</option>
                <option value=5>5</option>
            </select>
            <SaveMoviesButton @pass-movie-event="passMovie"/>
        </form>
    </div>
</template>
