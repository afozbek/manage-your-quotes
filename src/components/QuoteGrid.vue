<template>
    <div class="row">
        <app-quote v-for="quote in quotes" :key="quote.id">
            <span slot="quote">
                {{ quote.text }}
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
    }
}
</script>

<style lang="scss" scoped></style>
