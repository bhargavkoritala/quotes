<template>
    <div class='quoteDiv'>
        <label for="quote">Quote:</label>
        <textarea v-model="quote" class="form-control" rows="3" id="quote"></textarea>
        <button class="m-1 btn btn-primary" @click='addQuote'>Add quote</button>
    </div>    
</template>

<script>
export default {
    name:'AddQuote',
    data(){
        return{
            quote : ''
        }
    },
    methods:{
        addQuote(){
            this.$emit('newQuote', this.quote)
            this.quote=''
        }
    }
}
</script>

<style scoped>
    textarea{
        margin: auto;
    }
    .quoteDiv{
        width: 50%;
        margin: auto;
    }
    label{
        float: left;
    }
    
</style>