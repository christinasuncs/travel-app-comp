<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>Invoices</h1>
  </div>
</template>

<script>
import { onBeforeRouteLeave } from "vue-router"
export default {
  setup() {
    onBeforeRouteLeave(() => {
      const answer = window.confirm(
        "Are you sure you want to leave? Invoices are super awesome!"
      )
      if (!answer) return false
    })
  },
}
</script>
