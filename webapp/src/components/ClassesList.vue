<template>
  <v-card>
    <v-card-title class="pb-0">My Classes</v-card-title>
    <v-select
      :items="terms"
      dense
      solo
      item-text="text"
      item-value="term"
      v-model="term"
      hide-details
      class="mx-2"
    ></v-select>
    <v-list dense>
      <v-list-item
        v-for="(c, i) in classes"
        :key="i"
      >
        <v-list-item-content class="pa-0">
          <v-col cols="auto" class="pa-0">
            <v-chip :color="c.color">{{ c.text }}</v-chip>
          </v-col>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    
    <v-btn
      text
      block
      class="grey lighten-2 add-btn"
    >+ Add Class</v-btn>
  </v-card>
</template>

<style scoped>
  .add-btn {
    border-top-left-radius: 0;
    border-top-right-radius: 0;
  }
</style>

<script>
import AddClassMenu from '@/components/AddClassMenu'
import { getCurTerm } from '@/utils/util.js'

export default {
  name: 'ClassesList',

  props: {
    classes: { type: Array, required: true },
    terms: { type: Array, required: true },
  },

  components: {
    AddClassMenu,
  },

  watch: {
    terms() {
      if (this.terms.length > 0) {
        // set to current term
        this.term = getCurTerm()
      }
    },
  },

  data() {
    return {
      term: '',
    }
  },
}
</script>