<template>
    <div>
        <img src="https://cdn.pixabay.com/photo/2014/11/08/01/20/bald-eagle-521492__180.jpg" alt="Hello there" class="center">
        <p>{{ msg }}</p>
    </div>
</template>

<script>
export default {
    name: 'HelloThere',
    props: {
        msg: String
    }
}
</script>

<style>
p {
    font-family: "Arial", sans-serif;
    font-size: 90px;
    text-align: center;
    font-weight: bold;
}

.center {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 50%;
}
</style>