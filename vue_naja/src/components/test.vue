<template>
    <div class="hello">
        <h1>{{ mrg }}</h1>
     
        <h2>name</h2>
        <h2>email</h2>
        <p>==========================================</p>
        <h3>wasdwasdwasd</h3>
    </div>
</template>

<script>
export default {
    name: 'Test',
    props: {
        mrg: String
    }
}
</script>

<style scoped>

h2 {
    color: aqua;
}
p {
    color: blue;
}
</style>
