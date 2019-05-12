<template>
    <div class="quote mt-5 text-center">
        <label for="quote">Quote</label>
        <textarea name="quote" cols="100" rows="5" class="m-auto" v-model="message"></textarea>
        <button class="btn btn-primary mt-2" @click="handler">Add Quote</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: '',
                list: ['Just a Quote to start with something']
            }
        },
        methods: {
            passQuote() {
                // send the data from our array to parent element using $emit
                this.$emit('quoteWasPassed', this.list);
            },


            getQuote() {
                // simple input validation
                if(this.message === '') {
                    return alert('Please enter something in the quote field')
                }

                // Remove enter key from input value
                // This is weird since I never got that problem in vanilla JS
                this.message = this.message.replace(/\n/g, "");


                if(this.list.length === 10) {
                    alert('You reached out the limit please delete some of your quotes!');
                    this.message='';
                    return;
                } else {
                    this.list.push(this.message);
                }

                //clear input value
                this.message='';
            },



            handler() {
                this.getQuote();
                this.passQuote();
            }
        },

        created() {
            this.passQuote();
        }

    }
</script>

<style scoped>
    textarea {
        display: block;
    }
</style>