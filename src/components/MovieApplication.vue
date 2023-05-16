<script setup>
    import Movies from './Movies.vue'
    import {reactive, ref} from 'vue'
</script>

<template>
    <div id="app-container">
        <Movies />
    </div>
</template>


<style>
    #app-container {
        max-width: 600px;
        margin-left: auto;
        margin-right: auto;
    }

</style>