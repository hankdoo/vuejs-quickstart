<script >
export default {
  data() {
    return {
      firstName: 'hung',
      lastName: 'Do'
    }
  },
  computed: {
    fullName: {
      // getter
      get() {
        return this.firstName + ' ' + this.lastName
      },
      // setter
      set(newValue) {
        // Note: we are using destructuring assignment syntax here.
        [this.firstName, this.lastName] = newValue.split(' ')
      }
    }
  },
  methods: {
    say(message) {
      alert(message)
    },
    warn(message, event) {
      // now we have access to the native event
      if (event) {
        event.preventDefault()
      }
      alert(message)
    }
  }
}
</script>

<template>
  <div>
    <div>helllo</div>
    <p>{{ fullName.get }}</p>
    <button v-on:click="fullName.set"></button>
    <div>helllo</div>
    <button @click="say('hello')">Say hello</button>
    <button @click="say('bye')">Say bye</button>
    <button @click="warn('Form cannot be submitted yet.', $event)">
      Submit
    </button>

    <!-- using inline arrow function -->
    <button @click="(event) => warn('Form cannot be submitted yet.', event)">
      Submit
    </button>
  </div>
</template>

<style></style>