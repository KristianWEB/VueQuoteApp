<template>
    <div class="container">
       <progress-bar :progressData="list"></progress-bar>
        <quote-area @quoteWasPassed="list = $event"></quote-area>
        <!--  Send quote data to child quote.vue using props-->
        <card :quoteData="list"></card>
        <div class="alert alert-info mt-5 text-center" role="alert">
           Info: Click on a Quote to delete it
        </div>
    </div>


</template>

<script>
    import ProgressBar from './components/ProgressBar.vue';
    import Quote from './components/Quote.vue'
    import Card from './components/Card.vue'

    export default {
        data() {
            return {
                list: []
            }
        },


        components: {
            progressBar: ProgressBar,
            quoteArea: Quote,
            card: Card
        },


    }
</script>

<style scoped>


</style>
