<template>
  <div>
    <lifeCycle
      v-if="selectType === 'p-life-cycle'"
    ></lifeCycle>
    <response
      v-if="selectType === 'p-responsive'"
    ></response>
    <templateCompilation
      v-if="selectType === 'p-compilation'"
    ></templateCompilation>
    <virtualDom
      v-if="selectType === 'p-virtual-dom'"
    ></virtualDom>
  </div>
</template>

<script>
import lifeCycle from "./lifeCycle.vue"
import response from "./response.vue"
import templateCompilation from "./templateCompilation.vue"
import virtualDom from "./virtualDom.vue"
export default {
  components: {
    lifeCycle,
    response,
    templateCompilation,
    virtualDom,
  },
  props: {
    selectType: {
      type: String,
      required: true,
    },
  },
}
</script>

<style></style>
