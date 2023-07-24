<template>
  <button @click="onClick()" v-bind:style="{ background: color }" class="btn">
    {{ title }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: {
      type: String,
      default: "click me!",
    },
    color: {
      type: String,
    },
  },
  methods: {
    onClick() {
      console.log("click");
    },
  },
};
</script>

