<template>
    <div class="progress-bar">
        <div :style="cssProps" class="progress-bar-content">
            <span>{{ text }} - {{ percentage }}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        percentage: {
            type: String
        },
        text: {
            type: String
        }
    },
    computed: {
        cssProps() {
            return {
                '--percentage': this.percentage,
            }
        }
    }
}
</script>


<style scoped>
.progress-bar {
    background-color: transparent;
    border: 2px solid #001a68;
    border-radius: 30px;
    padding: 3px;
    margin: 10px 0;
}

.progress-bar-content {
    text-align: left;
    font-size: 1.2rem;
    color: #f1f1f1;
    padding-left: 12px;
    border-radius: 30px;
    background-color: #001a68;
    height: 30px;
    transition: 0.3s;

    animation: progress-animation ease 3s;
    width: var(--percentage);
}

@keyframes progress-animation {
    0% {width:0px;}
    100% {width: var(--percentage);}
}

</style>