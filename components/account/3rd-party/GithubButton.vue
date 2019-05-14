<template>
  <v-btn type="button" class="btn" v-on:click.prevent="GithubButton" v-text="label">
  </v-btn>
</template>

<script>
export default {
  name: 'GithubButton',
  props: {
    label: {
      required: true
    }
  },
  methods: {
    GithubButton () {
      this.$store.dispatch('userGithubLogin')
    }
  }
}
</script>
