<template>
<!-- Aufgabe 1 und Pro Aufgabe -->
  <div class="slot-style" :style="style()">
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    bgColor: {
      type: String,
    },
    color: {
      type: String,
    },
    width: {
      type: String,
    },
    height: {
      type: String,
    },
  },
  methods: {
      style() {
          return `background-color:${this.bgColor}; color:${this.color}; height:${this.height}; width:${this.width};`
      }
  },
};
</script>
<style scoped>
.slot-style {
  padding: 15px;
  width: 300px;
  height: 300px;
  box-shadow: 0 3px 5px -1px rgba(0, 0, 0, 0.2),
    0 6px 10px 0 rgba(0, 0, 0, 0.14), 0 1px 18px 0 rgba(0, 0, 0, 0.12);
}
</style>
