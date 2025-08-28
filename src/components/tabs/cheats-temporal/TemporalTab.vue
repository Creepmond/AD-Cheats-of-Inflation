<script>
import PrimaryToggleButton from "@/components/PrimaryToggleButton";

export default {
  name: "TemporalTab",
  components: {
    PrimaryToggleButton,
  },
  data() {
    return {

    };
  },
  computed: {
    
  },
  watch: {

  },
  methods: {
    update() {

    }
  }
};
</script>

<template>
  <div class="l-options-tab">
    <div class="l-options-grid">
      <div class="l-options-grid__row">
        <PrimaryToggleButton
          class="o-primary-btn--option l-options-grid__button"
          label="Hotkeys:"
          on="Enabled"
          off="Disabled"
        />
        <PrimaryToggleButton
          class="o-primary-btn--option l-options-grid__button l-toggle-button"
          label="Switch tabs on some events (e.g. entering challenges):"
        />
      </div>
      <div class="l-options-grid__row">
        <PrimaryToggleButton
          class="o-primary-btn--option l-options-grid__button"
          label="Offline progress:"
        />
        <div class="o-primary-btn o-primary-btn--option o-primary-btn--slider l-options-grid__button">
        </div>
        <PrimaryToggleButton
          class="o-primary-btn--option l-options-grid__button"
          label="Run suspended time as offline:"
        />
      </div>
      <div class="l-options-grid__row">
        <div
          class="o-primary-btn o-primary-btn--option o-primary-btn--slider l-options-grid__button"
        >
        </div>
      </div>
    </div>
  </div>
</template>