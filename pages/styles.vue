<template>
  <div v-html="content.template"></div>
  <!-- <component id="testing-area" v-if="!loading" :is="content"></component> -->
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      content: {
        template: ""
      }
    }
  },
  async fetch() {
    this.content = await fetch(
      'https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77338'
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
