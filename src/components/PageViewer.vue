<template>
    <div class="container">
        <h1>{{ page.pageTitle }}</h1>
        <p>{{ page.content }}</p>
    </div>
</template>

<script>
export default {
    // Options: holds data, computed properties methods
    props: ['page']
}


</script>