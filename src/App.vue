<template>
  <div id="app">
    <div class="container text-center mx-auto my-8">
      <loader-button
        @clicked="getData"
        class="mb-8"
        :text="chosenName ? 'New Name' : 'Get My Name'"
        :loading="loading"
      ></loader-button>
      <p v-if="error" key="error">Error... Please try again later</p>
      <p
        v-else-if="loading"
        key="loading"
        class="text-sm font-bold text-indigo-500"
      >
        Loading...
      </p>
      <transition name="fade">
        <p
          v-if="chosenName"
          key="name"
          class="text-4xl font-extrabold text-indigo-500"
        >
          {{ chosenName }}
        </p>
      </transition>
    </div>
  </div>
</template>

<script>
import LoaderButton from '@/components/LoaderButton.vue'

export default {
  components: { LoaderButton },
  data() {
    return {
      options: {
        count: 1,
        type: 'male',
        with_surname: true,
      },
      loading: false,
      error: false,
      chosenName: null,
    }
  },
  methods: {
    async getData() {
      this.loading = true
      this.error = false
      this.chosenName = null

      try {
        setTimeout(async () => {
          // const res = await fetch(
          //   'https://namey.muffinlabs.com/name.json?' + this.query
          // )
          // const data = await res.json()

          const data = ['John Johnson']

          this.chosenName = data[0]
          this.loading = false
        }, 1000)
      } catch (error) {
        console.log(error)
        this.loading = false
        this.error = true
      }
    },
  },
  computed: {
    query() {
      return Object.keys(this.options)
        .map(
          key =>
            encodeURIComponent(key) +
            '=' +
            encodeURIComponent(this.options[key])
        )
        .join('&')
    },
  },
}
</script>

<style></style>
