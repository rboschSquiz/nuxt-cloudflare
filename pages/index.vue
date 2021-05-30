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
      this.$axios.$get('https://nzdemos-web.squiz.cloud/jamstack/api/api-gateway/_nocache?id=77097', {})
      // this.$axios.$get('https://nzdemos-web.squiz.cloud/__api/assets/77097?data=attributes,contents', {
      //   headers: {
      //     'Authorization': 'Bearer 2a800c1a57ba66ea3cecf38c7359f606'
      //   }
      // })
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
