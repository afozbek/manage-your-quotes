<template>
    <div class="container">
        <app-new-quote @quoteCreated="createQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote" />

        <!-- INFO BOX -->
        <div class="col-sm-12 text-center">
            <div class="alert alert-info">
                INFO: Click on a Quote to delete it!
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue"
import NewQuote from "./components/NewQuote.vue"
import { uuid } from "vue-uuid"

export default {
    data() {
        return {
            maxQuote: 10,
            quotes: [{ id: uuid.v1(), quote: "Simple quote" }]
        }
    },
    components: {
        appQuoteGrid: QuoteGrid,
        appNewQuote: NewQuote
    },
    methods: {
        createQuote(quote) {
            this.quotes = [...this.quotes, { id: uuid.v1(), quote }]
        },
        deleteQuote(quoteId) {
            this.quotes = this.quotes.filter(quote => quote.id !== quoteId)
        }
    }
}
</script>

<style></style>
