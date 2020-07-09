<template>
  <div>
    <h1>Event #{{ id }}</h1>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: '_id',
  computed: {
    id() {
      return this.$route.params.id
    },
  },
  head() {
    return {
      title: `Event #${this.id}`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'You can create Event here',
        },
      ],
    }
  },
}
</script>

<style scoped></style>
