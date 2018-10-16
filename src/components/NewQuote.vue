<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group just-cent">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>

        </form>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ''
            };
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>
    .just-cent {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .btn {
        margin-top: 30px;
    }
    form  {
        margin-top: 20px;
        width: 100%;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    textarea {
        min-width: 300px;
        min-height: 200px;
    }
</style>