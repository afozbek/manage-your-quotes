<template>
    <div class="container">
        <quote-grid :quotes="quotes" />
    </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue"

export default {
    data() {
        return {
            maxQuote: 10,
            quotes: [{ id: 1, text: "Simple quote" }]
        }
    },
    components: {
        quoteGrid: QuoteGrid
    }
}
</script>

<style></style>
