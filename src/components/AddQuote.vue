<template>

        <form>
            <div class="form-group">
                <label for="quote">Quote:</label>
                <textarea class="form-control" rows="3" id="quote"></textarea>
            </div>
            <button class="btn btn-primary" type="submit">Add quote</button>
        </form>

</template>

<script>
export default {
    name:'AddQuote'
}
</script>

<style scoped>
    textarea{
        margin: auto;
    }
    form{
        width: 50%;
        margin: auto;
    }
    label{
        float: left;
    }
    
</style>