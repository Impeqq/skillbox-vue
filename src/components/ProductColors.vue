<template>
  <ul class="colors">
    <li class="colors__item" v-for="color in arrayOfColors" :key="color.id">
      <label class="colors__label">
        <input
          class="colors__radio sr-only"
          type="radio"
          :value="color.id"
          v-model="computedColor"
        />
        <span class="colors__value" :style="`background-color: ${color.code}`">
        </span>
      </label>
    </li>
  </ul>
</template>

<script>
export default {
  name: "ProductColors",
  props: ["arrayOfColors", "currentColor"],
  computed: {
    computedColor: {
      get() {
        return this.currentColor;
      },
      set(value) {
        this.$emit("update:currentColor", value);
      },
    },
  },
};
</script>