<script>
export default {
  name: "TemporalSkipButton",
  props: {
    label: {
      type: String,
      required: true,
    },
  },
};
</script>

<template>
  <button
    class="o-primary-btn o-primary-btn--cheats"
  >
    {{ label }}
  </button>
</template>

<style>
.o-primary-btn--cheats {
  font-size: 20px;
  height: 65px;
  width: 85vw;
  max-width: 210px;
}
</style>