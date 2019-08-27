<template>
     <div class="row">
          <form>
               <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                    <label for="quote">Quote</label>
                    <textarea name="quote" v-model="citat" rows="3" class="form-control"></textarea>
               </div>

               <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                    <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
               </div>

          </form>
     </div>
</template>

<script>
export default {
     data() {
          return {
               citat: ''
          }
     },

     methods: {
          createNew() {
              this.$emit('citatDodat', this.citat) // da mozemo iz parenta da pristupimo ovom metodu preko naseg eventa koji cmeo pozvati u <app-new-quote> u App.vue
              this.citat = ''
          }
     }
}
</script>

<style>

</style>