<script >
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      }
    }
  },

  computed: {
    // a computed getter
    publishedBooksMessage() {
      // `this` points to the component instance
      return this.author.books.length > 0 ? 'Yes' : 'No'
    },
    now() {
      return Date.now()
    }
  },
  methods: {
    calculateBooksMessage() {
      return this.author.books.length > 0 ? 'Yes' : 'No'
    }
  }

}


</script>

<template>
  <div>
    <div>{{ author.name }}</div>
    <span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span>
    <span>{{ publishedBooksMessage }}</span>
    <p>{{ calculateBooksMessage() }}</p>
    <p>{{ now }}</p>
  </div>
</template>

<style></style>