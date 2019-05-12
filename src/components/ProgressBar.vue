<template>
    <div class="progress mt-4">
        <div class="progress-bar" role="progressbar" :style="{width: (progressData.length * 10)+'%'}">{{
            progressData.length
            }}/10</div>
    </div>
</template>

<script>
    export default {
        props: ['progressData'],

    }
</script>

<style scoped>

</style>