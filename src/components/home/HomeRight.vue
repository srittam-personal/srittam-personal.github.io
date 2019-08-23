<template>
    <li>
        <img :src="product.url" alt="">
    </li>
</template>

<script>
    export default {
        props:[
            'product'
        ]
    }
</script>

<style lang="scss" scoped>

</style>