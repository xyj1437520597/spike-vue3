<demo>
</demo>
<template>
  <div class="icon-demo">
    <s-pager :total="7" v-model:current="current"></s-pager>
  </div>
</template>

<script lang="ts">
import { sPager } from "spike-vue3"
import { ref } from "vue"
export default {
  components: {
    sPager
  },
  setup() {
    const current = ref(1)
    return {
      current
    }
  }
}
</script>

