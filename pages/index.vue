<template>
  <div>
    <h1>Events</h1>

    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard'
export default {
  components: {
    EventCard,
  },
  asyncData({ $axios, error }) {
    return $axios
      .get('http://localhost:8080/events')
      .then((resp) => {
        return {
          events: resp.data,
        }
      })
      .catch((e) => {
        error({
          statusCode: 503,
          message: 'Unable API server',
        })
      })
  },
  head() {
    return {
      title: 'Event Listening',
    }
  },
}
</script>
