<template>
     <div class="row">
          <div class="col-sm-12">
          <h3>Quotes Added</h3>
          <div class="progress">
               <div class="progress">
                    <div class="progress-bar" role="progressbar" aria-valenow="60" aria-valuemin="0" aria-valuemax="100"
                    :style="{ width: (brojCitata / maxCitati) * 100 + '%' }">
                         <!-- bootstrap klase/atributi. Osim ovog :style. Ono stavlja inline css tj style koji ce imati sirinu, recimo ako imam 5 citata, a max je 10, 5/10 je 5, pomnozim za 100 da dobijem 50, i dodam procenat, dakle width: 50% ce biti -->
                         {{ brojCitata }} / {{ maxCitati }}
                    </div>
               </div>
          </div>
          </div>
     </div>
</template>

<script>
export default {
     props: ['brojCitata', 'maxCitati'] // brojCitata cemo bajndovati, a bice arrQuotes.length, i maxCitati cemo bajndovati, a ono je maxQuotes tj 10
}
</script>

<style>

</style>