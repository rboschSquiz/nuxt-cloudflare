<template>
  <div v-html="content.template"></div>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      content: {
        template: ""
      },
      loading: true
    }
  },
  async fetch() {
    this.content = await fetch(
      'https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77105'
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
