<script>
import OpenModalHotkeysButton from "@/components/OpenModalHotkeysButton";
import TemporalSkipButton from "@/components/tabs/cheats-temporal/TemporalSkipButton.vue";

export default {
  name: "TemporalTab",
  components: {
    OpenModalHotkeysButton,
    TemporalSkipButton,
  },
};
</script>

<template>
  <div class="l-cheats-temporal-tab">
    <span class="l-temporal-introtext">
      This is a tab dedicated to modifying real-time/true-time.
    </span>
    <div class="l-cheats-skip-grid">
      <div class="l-cheats-skip-buttons">
        <TemporalSkipButton 
          label="Skip Hour"
          onclick="
            simulateTime(3600, false, true)
            Modal.hideAll()
          "
        />
        <TemporalSkipButton 
          label="Skip Day"
          onclick="
            simulateTime(3600 * 24, false, true)
            Modal.hideAll()
          "
        />
        <TemporalSkipButton 
          label="Skip Month"
          onclick="
            simulateTime(3600 * 24 * 30, false, true)
            Modal.hideAll()
          "
        />
        <TemporalSkipButton 
          label="Skip Year"
          onclick="
            simulateTime(3600 * 24 * 365, false, true)
            Modal.hideAll()
          "
        />
      </div>
    </div>
    <OpenModalHotkeysButton />
  </div>
</template>ks

<style>
.l-cheats-temporal-tab {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.l-cheats-skip-grid {
  height: 130px;
  width: 85vw;
  max-width: 1050px;
  margin: 10px auto;
  display: flex;
  justify-content: center;
}

.l-cheats-skip-buttons {
  width: 85vw;
  max-width: 1050px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.l-temporal-introtext {
  font-size: 12px;
  margin-top: 20px;
}
</style>