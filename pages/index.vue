<template>
<div>
  <!-- <button @click="loading = !loading" type="button">Show stuff</button> -->
  <div v-html="content.template"></div>
  <!-- <component v-bind:is="ssrContent.name"></component> -->
</div>
</template>

<script>

export default {
  data () {
    return {
      content: {
        template: '<div></div>'
      },
      loading: true
    }
  },
  async fetch() {
    this.content = await fetch(
      'https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77097'
    )
    .then(res => res.json())
    .then(data => {
      this.loading = false

      return {
        name: data.name,
        template: data.contents
      }
    })
  }
}
</script>
