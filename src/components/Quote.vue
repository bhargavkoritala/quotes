<template>
    <div class="border border-primary">
        <p>{{quote}}</p>
    </div>
</template>

<script>
export default {
    name:'Quote',
    props : {
        quote : String
    },
    data(){
        return{
            isHovering : false
        }
    },
    methods:{
        delQuote(){
            this.$emit('delQuote',this.quote)
        }
    }
}
</script>

<style scoped>
    div:hover{
        background-color: lightsalmon;
    }
    div{
        cursor: pointer;
    }
    .border{
        font-family: Brush Script MT, Brush Script Std, cursive;
    }
</style>