<template>
<header>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
</header>
</template>

<script>
export default {
    name : "Header",
};
</script>

<style lang="scss" scoped>
header  {
    height: 50px;
    background-color: #2e3a46;
    img {
        height: 100%;
        padding: 0.5em;
    }
}
</style>