<template>
    <div class="card">
        <img :src="projectData.image">
        <h3 class="mt-1">{{ projectData.name }}</h3>
        <h5>{{ projectData.tech}}</h5>
        <p>{{ projectData.description }}</p>
        <a class="card-btn" target="_blank" :href="projectData.link">Check it out</a>
    </div>
</template>

<script>
export default {
    props: {
        projectData: Object
    }
}
</script>

<style scoped>
.card {
    border-radius: 30px;
    background-color: rgb(240, 240, 240);
    box-shadow: 10px 10px 43px -14px rgba(0,0,0,0.75);
}

.card > img {
    border-radius: 30px;
}

.card-btn {
    border: none;
    padding: 5px;
    border-radius: 30px;
    background-color: #a647a6;
    margin: 0 4rem 0.7rem 4rem;
    color: #f1f1f1;
    transition-duration: 0.3s;
}

.card-btn:hover {
    text-decoration: none;
    background-color: #c757c7;
}
</style>