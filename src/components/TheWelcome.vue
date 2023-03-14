<script>
  export default {
    data() {
      return {
        listItems: []
      }
    },
    methods: {
      async getData() {
        const res = await fetch("https://fakestoreapi.com/products")
        const finalRes = await res.json();
        this.listItems = finalRes;
      }
    },
    mounted() {
      this.getData()
    }
  }
</script>

<template>
  <div v-for = "item in listItems" :key="item">
    {{ item.title }}
  </div>
</template>
