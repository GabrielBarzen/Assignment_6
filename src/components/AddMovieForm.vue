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
    <div id="container">
        <form action="post">
            
            <div class="row">
                <label for="title"  class="col-lg-1">Title:</label>
                <input type="text" class="input-group-text col-lg-3" name="title" id="title-input">
            </div>

            <div class="row">
                <label for="grade" class="col-lg-1">Grade:</label>
                <div class="col-lg-11">
                    <select class="input-group custom-select" name="grade" id="grade-input">
                        <option selected value="">Choose grade</option>
                        <option value=1>1</option>
                        <option value=2>2</option>
                        <option value=3>3</option>
                        <option value=4>4</option>
                        <option value=5>5</option>
                    </select>
                </div>
            </div>

            <SaveMoviesButton @pass-movie-event="passMovie"/>
        </form>
    </div>
</template>

<style>

#title-input {
    /* padding: 0 !important; */
    margin: 0 12px;


}
</style>