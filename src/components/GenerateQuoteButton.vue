<template>
  <ChildComponent v-bind:dataForChild='studentsArray' />
</template>

<script>
  export default {
    name: App,
    components: {
      ChildComponent
    },
    data(){
      return {
        studentsArray: [1,2,3,4,5]
      }
    }
  }
</script>