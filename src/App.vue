<template>
    <div class="container">
        <app-header-new :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header-new>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuotesGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import HeaderNew from './components/HeaderNew.vue';
    
    export default {
        data: function () {
            return {
                quotes: [
                    'Default quote'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete Quotes first!');
                }
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeaderNew: HeaderNew
        }
    }
</script>

<style>
</style>
