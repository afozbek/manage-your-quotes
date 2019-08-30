<template>
    <div class="container">
        <app-header
            :maxQuotes="maxQuote"
            :quoteCount="quotes.length"
        ></app-header>
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
import Header from "./components/Header.vue"
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
        appHeader: Header,
        appQuoteGrid: QuoteGrid,
        appNewQuote: NewQuote
    },
    methods: {
        createQuote(quote) {
            if (this.quotes.length >= this.maxQuote) {
                return alert(
                    "You have reached your max quote limit 😥 Please delete some quotes in order to add new quote"
                )
            }
            this.quotes = [...this.quotes, { id: uuid.v1(), quote }]
        },
        deleteQuote(quoteId) {
            this.quotes = this.quotes.filter(quote => quote.id !== quoteId)
        }
    }
}
</script>

<style></style>
