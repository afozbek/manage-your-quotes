<template>
    <div class="row">
        <app-quote
            v-for="quote in quotes"
            :key="quote.id"
            @click.native="deleteQuote(quote.id)"
        >
            <span slot="quote">
                {{ quote.quote }}
            </span>
        </app-quote>
    </div>
</template>

<script>
import Quote from "./Quote.vue"

export default {
    props: {
        quotes: {
            type: Array,
            required: true
        }
    },
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(id) {
            this.$emit("deleteQuote", id)
        }
    }
}
</script>

<style lang="scss" scoped></style>
