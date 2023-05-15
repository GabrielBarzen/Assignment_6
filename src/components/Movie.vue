
<script setup>
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        if (confirmed) e.target.parentElement.parentElement.remove();

    }
</script>

<template>
    <li>

        <div>
            <span>
                ExampleText
            </span>
            <span>
                *****
            </span>
            <span @click="remove">
                x
            </span>
        </div>
    </li>
</template>
