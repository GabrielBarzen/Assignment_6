<script setup>
    const emit = defineEmits(['order-alpha'])
    
    function orderByAlphabetic() {
        emit("order-alpha");
    }
</script>

<template>
    <div>
        <button class="btn btn-primary" @click="orderByAlphabetic">Order Alphabetic</button>
    </div>
</template>

