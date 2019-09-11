<template>

<div class = "slider_container">
    <div class = "slides" v-for = "slide in slides" :key = "slide.id" v-bind:style = "slide.style">
        <div class = "slides_text">{{ slide.text }}</div>
        <div class = "slides_subtext">{{ slide.subtext }}</div>
    </div>
</div>

</template>

<script>
import TweenLite from 'gsap';

export default {
    name: 'Slider',
    props: {
        slides: Array
    },
    mounted: function() {
        TweenLite.from([".slides_text", ".slides_subtext"], 3, { 
            opacity: 0
        })
    }
}
</script>

<style>
.slider_container {
    background-size: 100% 100%;
    background-repeat: no-repeat;
    color: white;

}

.slides, .slider_container {
    height: 500px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.slides_text {
    font-size: 36px;
    font-weight: bold;
}

.slides_subtext { 
    font-size: 18px;
}

</style>
