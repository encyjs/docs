<template lang='pug'>
  div.guide-page
    GuidePage(
      contentLabel="Ency"
      routeName="/ency"
      :pages="lessons"
    )
      nuxt-child
</template>

<script>
import GuidePage from '~/components/GuidePage'

export default {
  asyncData: async ({ app }) => {
    return {
      lessons: await app.$content('/ency').getAll()
    }
  },
  components: {
    GuidePage
  }
}
</script>
