<template>
    <h1>Email: {{ email }}</h1>
    <h1>Email: {{ mobile }}</h1>
    <h1>Email: {{ mobile=8888 }}</h1>

</template>

<script>

export default {
    data() {
        return {
            email: "satyam@gmail.com",
            mobile: 9999 
        }
    }
}

</script>

<style>
h1{
    color: red;
}

</style>