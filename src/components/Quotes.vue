<template>
    <div class="row justify-content-between">
        <div class="p-2 col-lg-3 col-md-3 col-sm-3 delete" :key="index" v-for="(quote,index) in quotes">
            <app-quote @click.native="deleteQuote(quote)" :quote="quote"></app-quote>
        </div>
    </div>
</template>

<script>
import Quote from './Quote.vue'

export default {
    name:'Quotes',
    props : {
        quotes : Array
    },
    components:{
        appQuote : Quote
    },
    data(){
        return{
            isHovering: false
        }
    },
    methods:{
        deleteQuote(quote){
            this.$emit('del-quote', quote)
        }
    }
}
</script>

<style scoped>
    .red{
        background-color: lightsalmon;
    }
    
</style>