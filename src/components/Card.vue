<template>
    <div class="col py-4 g-3 mx-3 flex">
                <img :src="poster" :alt="title">
                <h2>{{ title }}</h2>
                <h3>{{ author }}</h3>
                <h4>{{ year }}</h4>
            </div>
</template>

<script>
export default {
    name: 'Card',
    props: [
        'poster',
        'title',
        'author',
        'genre',
        'year',
    ],
};
</script>