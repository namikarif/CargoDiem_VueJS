<template>
  <div v-show="isActive" v-on:click="$emit('clickTab', $event)">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Tab",
  props: {
    name: {required: true},
    selected: {default: false}
  },
  data() {
    return {
      isActive: false
    };
  },
  computed: {
    href() {
      return '#' + this.name.toLowerCase().replace(/ /g, '-');
    }
  },
  mounted() {
    this.isActive = this.selected;
  }
}
</script>

<style scoped>

</style>
