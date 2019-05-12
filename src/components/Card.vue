<template>

<div class="row">
    <div  v-for="(item,index) in quoteData" class="col-3 mt-3" @click="deleteCard(index)">
        <div class="card">
            <div class="card-body">
                <p class="card-text text-center">{{ item }}</p>
            </div>
        </div>
    </div>
</div>

</template>

<script>
    export default {
        props: ['quoteData'],

        methods: {
            deleteCard(index) {
                this.quoteData.splice(index, 1);
            }
        }
    }
</script>

<style scoped>

</style>