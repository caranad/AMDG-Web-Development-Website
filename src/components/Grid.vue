<template>
    <div class = "amdg_grid_item">
        <div class = "amdg_grid_image">
            <img :src = "imageUrl">
        </div>

        <div class = "amdg_grid_content" v-if = "type == 'text'">
            <h1>{{ title }}</h1>
            <p> {{ content }}</p>
        </div>

        <div class = "amdg_grid_content" v-if = "type == 'list'">
            <h1>{{ title }}</h1>
            <h2>{{ subtitle }}</h2>
            <ul v-for = "thing in content" :key = "thing.id">
                <li>{{ thing }}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Grid',
    props: {
        title: String,
        content: [String, Array],
        subtitle: String,
        imageUrl: String,
        type: String
    }
}
</script>

<style>
.amdg_grid_item {
    border: 1px solid black;
    box-shadow: 2px 2px gray;
    margin-right: 10px;
    height: 100%;
    padding: 10px;
    background-color: white;
    color: black;
}

.amdg_grid_image {
    width: 200px;
    height: 200px;
    margin: 0 auto;
}

.amdg_grid_image img {
    width: 100%;
    height: 100%;
}
</style>
