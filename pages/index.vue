<template>
  <!-- <button @click="loading = !loading" type="button">Show stuff</button> -->
  <div v-html="content.template"></div>
  <!-- <component v-bind:is="ssrContent.name"></component> -->
</template>

<script>

export default {
  data () {
    return {
      content: {
        template: '<div></div>'
      }
    }
  },
  async fetch() {
    this.content = await fetch(
      'https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77097'
    )
    .then(res => res.json())
    .then(data => {
      return {
        name: data.name,
        template: data.contents
      }
    })
  }
}
</script>
