<template>
    <div :class="{red:isHovering}" class="border border-primary">
        <p @click="delQuote" @mouseover="isHovering=!isHovering" @mouseout="isHovering=!isHovering">{{quote}}</p>
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
    .red{
        background-color: lightsalmon;
    }
    p{
        cursor: pointer;
    }
    .border{
        font-family: Brush Script MT, Brush Script Std, cursive;
    }
</style>