<script setup>
    let props = defineProps(["title", "grade", "id"]);
    const emit = defineEmits(['movie-remove'])
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        // if (confirmed) e.target.parentElement.parentElement.parentElement.remove();
        emit("movie-remove",props.id)
    }

</script>

<template>
    <li>
        <div id="movie">
            <span id="title">
                {{title}}
            </span>
            <span id="stars">
                <img v-for="grade of props.grade" src="./icons/star.png">
            </span>
            <span>
                <img src="./icons/delete.png" @click="remove"/>
            </span>
        </div>
    </li>
</template>


<style>
li {
    list-style: none;
    font-size: 1.2rem;
    text-align: center;
    background-color: lightgray;
    margin: 5px 0;
    width: 100%;
    border: 1px solid grey;
    border-radius: 5px;
    padding: 5px;
}

img {
    max-width: 20px;
}

#title {
    width: 100%;
    text-align: left;
}

#movie {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

#stars {
    display: flex;
    min-width: 150px;
    justify-content: end;
    align-items: center;
    margin-right: 20px;
}

</style>
