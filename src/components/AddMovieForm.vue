
<script setup>
    import SaveMoviesButton from './SaveMoviesButton.vue'
</script>

<template>
    <div>
        <form action="post">
            <label for="title">Title:</label>
            <input type="text" class="input-group-text" name="title" id="title-input">
            <label for="grade">Grade:</label>
            <select class="input-group custom-select" name="grade" id="grade-input">
                <option selected>Choose grade</option>
                <option>1</option>
                <option>2</option>
                <option>3</option>
                <option>4</option>
                <option>5</option>
            </select>
        </form>
    </div>
    <div>
        <SaveMoviesButton />
    </div>
</template>
