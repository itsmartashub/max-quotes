<template>
  <div class="container">
      <app-header :brojCitata="arrQuotes.length" :maxCitati="maxQuotes"></app-header>
      <app-new-quote @citatDodat="noviCitat"></app-new-quote>
      <!-- ovde smo kreirajuci ovaj citatDodat event prosledili i neki podatak, a to je this.citat tj citat koji je trenutno kreiran. Mozemo ovde staviti noviCitat($event) ali i ne moramo jer ce vue.js to implicintno da uradi, mozemo samo dole u metodu da stavimo kao argument -->
      <app-quote-grid :quotes="arrQuotes" @citatObrisan="obrisatiCitat"></app-quote-grid>

      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Info: Click on a Quote to delete it!
          </div>
        </div>
      </div>
  </div>
</template>

<script>
  import QuoteGrid from "@/components/QuoteGrid.vue"
  import NewQuote from "@/components/NewQuote.vue"
  import Header from "@/components/Header.vue"

  export default {
    // name: 'app',
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    },

    data() {
      return {
        arrQuotes: [
          'Just a Quote to see something'
        ],
        maxQuotes: 10
      }
    },

    methods: {
      noviCitat(citat) {
        if(this.arrQuotes.length >= this.maxQuotes)
          return alert('Please delete quotes first')

        this.arrQuotes.push(citat)
      },

      obrisatiCitat(indexCitata) {
        this.arrQuotes.splice(indexCitata, 1) // dakle idi u arrQuotes niz, nadji el sa brojem indexa koji je jednak broju indexCitata, i splajsuj tj obrisi jedan element 
      }
    }
  }
</script>
