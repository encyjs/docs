<template lang='pug'>
  div.guide-page
    GuidePage(
      contentLabel="Vuency"
      routeName="/vuency"
      :pages="lessons"
    )
      nuxt-child
</template>

<script>
import GuidePage from '~/components/GuidePage'

export default {
  asyncData: async ({ app, payload }) => {
    return {
      lessons: payload || await app.$content('/vuency').getAll()
    }
  },
  components: {
    GuidePage
  }
}
</script>
