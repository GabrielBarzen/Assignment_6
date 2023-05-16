
<script setup>
    const emit = defineEmits(['order-grade'])
    
    function orderByGrade() {
        emit("order-grade");
    }
</script>

<template>
    <div>
        <button class="btn btn-primary" @click="orderByGrade">Order Grade</button>
    </div>
</template>

<style scoped>
</style>
