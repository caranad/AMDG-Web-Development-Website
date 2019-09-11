<template>

<div class = "header_container">
    <ul>
        <li v-for = "link in links" :key = "link.id">
            <a :href = "link.goTo">{{ link.text }}</a>
        </li>
    </ul>
</div>

</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            links: [
                {
                    "id": 0,
                    "text": "HOME",
                    "goTo": "/"
                },
                {
                    "id": 1,
                    "text": "ABOUT",
                    "goTo": "#about"
                },
                {
                    "id": 2,
                    "text": "PROJECTS",
                    "goTo": "#projects"
                },
                {
                    "id": 3,
                    "text": "PRICING",
                    "goTo": "#pricing"
                },
                {
                    "id": 4,
                    "text": "CONTACT",
                    "goTo": "#contact"
                },
            ]
        }
    }
}
</script>

<style>

.header_container {
    width: 100%;
    background-color: white;
    position: fixed;
    text-align: right;
    border-bottom: 3px solid gray;
}

.header_container ul li {
    display: inline-block;
    padding: 15px;
}

.header_container ul li a {
    color: blue;
    text-decoration: none;
    font-weight: bold;
}

</style>
