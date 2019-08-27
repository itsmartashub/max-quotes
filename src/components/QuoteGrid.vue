<template>
  <div class="row">
      <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
      <!-- ne mozemo staviti samo @click na ovu appQuote komponentu, moramo da stavimo native modifikator koji govori vuejsu da reaguje na klik na komponentu ako se desi klik na native element te komponente. Dakle on registruje klik koji se desio u Quote.vue template-u, na neki od elemenata. Ovom click metodu cemo kao parametar proslediti index ovog v-fora, da se zna na koji smo el kliknuli, sa kojim indexom, da zna koji el da obrise -->
  </div>
</template>

<script>
  import Quote from '@/components/Quote.vue'

  export default {
    // name: 'QuoteGrid',

    props: ['quotes'], // bajdnovali smo arrQuotes iz parent component App.vue i prosledili ga kao props quotes

    components: {
        appQuote: Quote // ovde u QuoteGrid koristimo Quote.vue component
    },

    methods: {
      deleteQuote(index) {
        this.$emit('citatObrisan', index) // idemo App.vue u <app-quote-grid> component da osluskujemo ovaj kreirani event
      }
    }
    
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
