
<script setup>
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        if (confirmed) e.target.parentElement.parentElement.remove();
    }
    
    const props = defineProps({"title":String,"grade":String})
    console.log(props)
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
