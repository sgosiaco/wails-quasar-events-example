<template>
  <q-page class="flex flex-center column q-gutter-y-lg">
    <img alt="Quasar logo" src="~assets/quasar-logo-vertical.svg" style="width: 200px; height: 200px">
    <q-chip color="primary" text-color="white">
      The current count is: {{ seconds }}
    </q-chip>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { EventsOn } from 'app/wailsjs/runtime/runtime'

export default defineComponent({
  name: 'IndexPage',
  setup() {
    const seconds = ref(0)

    EventsOn("second", (time) => {
      seconds.value = time
    })

    return {
      seconds
    }
  }
})
</script>
