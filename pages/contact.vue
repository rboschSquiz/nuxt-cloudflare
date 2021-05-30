<template>
  <component id="testing-area" v-if="!loading" :is="content"></component>
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
  mounted: function () {
    this.getContent()
  },
  methods: {
    getContent: function () {
      // this.$axios.$get('https://nzdemos-web.squiz.cloud/jamstack/home?SQ_PAINT_LAYOUT_NAME=json&SQ_DESIGN_NAME=json', {})
      this.$axios.$get('https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77105', {})
        .then((data) => {
          this.content = {
            template: `${data.contents}`,
            data () {
              return {
                value: true
              }
            }
          }

          this.loading = false
        })
    }
  }
}
</script>
