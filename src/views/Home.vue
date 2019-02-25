<template>
  <div>
    <AppHeader />
    <Quote v-for='(quote, i) in quotes' v-bind:ronQuote='quote' v-bind:key='"ron"+ i'/>
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
import Quote from '../components/Quote.vue'


export default {
  data() {
    return {
      quotes:''
    }
  },
  components: {
    AppHeader,
    Quote
  },
  methods: {
    fetchQuote() {
      fetch('https://ron-swanson-quotes.herokuapp.com/v2/quotes/2')
      .then(resp => resp.json())
      .then(resp => (this.quotes = resp));
    }
  },
    mounted() {
    this.fetchQuote()
  }
}
</script>

<style scoped>

</style>



