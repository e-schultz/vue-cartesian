<template>
  <div>
    <button :disabled="disabled" v-bind:style="{ backgroundColor: color }">{{label}}</button>
  </div>
</template>
<script>
export default {
  name: "BaseButton",
  props: ["label", "disabled", "color"]
};
</script>
