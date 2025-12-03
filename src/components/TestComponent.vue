<script lang="ts">
import { createApp, defineComponent } from 'vue'

export default defineComponent({
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
  data() {
    return {}
  },
  methods: {
    getTemplate() {
      const app = createApp({})
      return app.component('TestComponent', {
        data: () => {
          return {
            msg: this.msg as string,
          }
        },
        methods: {
          getMessage(): string {
            return this.msg
          },
        },
        template: `<div></div>`,
      })
    },
  },
})
</script>

<template>
  <div></div>
</template>

<style scoped></style>
