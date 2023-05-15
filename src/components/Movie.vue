
<script setup>
    let props = defineProps(["title", "grade"]);
    
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        if (confirmed) e.target.parentElement.parentElement.parentElement.remove();

    }



</script>

<template>
    <li>
        <div>
            <span>
                {{title}}
            </span>
            <span v-for="grade of props.grade">
                <img src="./icons/star.png">
                
            </span>
            <span>
                <img src="./icons/delete.png" @click="remove"/>
            </span>
        </div>
    </li>
</template>
