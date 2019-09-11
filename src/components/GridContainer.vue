<template>
    <div class = "amdg_grid_container">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'GridContainer'
}
</script>

<style>
.amdg_grid_container {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
}
</style>
