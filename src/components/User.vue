<template>
    <p>The user is {{age}} years old</p>
</template>

<script>
export default {
    name: "user-comp",
    props: ["age"]
}
</script>

<style scoped>
p {
    color: #b60c61;
    font-size: 20px;
    font-weight: bold;
}
</style>
