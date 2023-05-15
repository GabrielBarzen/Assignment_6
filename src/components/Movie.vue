
<script setup>
    defineProps(["title", "grade"]);
    
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        if (confirmed) e.target.parentElement.parentElement.remove();

    }
</script>

<template>
    <li>
        <div>
            <span>
                {{title}}
            </span>
            <span>
                {{grade}}
            </span>
            <span @click="remove">
                x
            </span>
        </div>
    </li>
</template>
