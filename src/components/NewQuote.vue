<template>
    <div class="row">
        <form action="">
            <div
                class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3"
            >
                <label for="">Quote</label>
                <textarea
                    class="form-control"
                    rows="3"
                    v-model="quote"
                ></textarea>
            </div>
            <div
                class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3"
            >
                <button class="btn btn-primary" @click.prevent="createQuote">
                    Add Quote
                </button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            quote: ""
        }
    },
    methods: {
        createQuote() {
            this.$emit("quoteCreated", this.quote)
            this.quote = ""
        }
    }
}
</script>

<style></style>
