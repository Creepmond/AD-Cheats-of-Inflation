<script>
import ModalWrapperChoice from "@/components/modals/ModalWrapperChoice";

export default {
  name: "HardResetModal",
  components: {
    ModalWrapperChoice
  },
  data() {
    return {
      input: ""
    };
  },
  computed: {
    willHardReset() {
      return this.input === "Shrek";
    },
    hasExtraNG() {
      return player.records.fullGameCompletions > 0;
    },
    hasSpeedrun() {
      return player.speedrun.isUnlocked;
    }
  },
  destroyed() {
    if (this.willHardReset) SecretAchievement(38).unlock();
  },
  methods: {
    hardReset() {
      if (this.willHardReset) GameStorage.hardReset();
      this.input = "";
    },
  },
};
</script>

<template>
  <ModalWrapperChoice
    :show-cancel="!willHardReset"
    :show-confirm="willHardReset"
    confirm-class="o-primary-btn--width-medium c-modal__confirm-btn c-modal-hard-reset-btn"
    @confirm="hardReset"
  >
    <template #header>
      HARD RESET
    </template>
    <div class="c-modal-message__text">
      Please confirm your desire to reset this save slot. <br /> 
      <span class="c-modal-hard-reset-danger">Deleting your save will not unlock anything secret.</span> <br /> 
      Type in "Shrek" to confirm. <br />
      This will wipe EVERYTHING on your save except for Options. <br />
      To do that, manually perform "dev.harshReset()" on your console.
      <div class="c-modal-hard-reset-danger">
        <span v-if="hasExtraNG">
          <br>
          This will also remove any Glyph cosmetics you have unlocked from completing the game!
        </span>
        <span v-if="hasSpeedrun">
          <br>
          You will lose the ability to do a Speedrun. To restart your run, use the "Start Speedrun" button instead.
        </span>
      </div>
    </div>
    <input
      ref="input"
      v-model="input"
      type="text"
      onpaste="return false;"
      class="c-modal-input c-modal-hard-reset__input"
      @keyup.esc="emitClose"
    >
    <div class="c-modal-hard-reset-info">
      <div
        v-if="willHardReset"
        class="c-modal-hard-reset-danger"
      >
        Phrase confirmed - continuing will irreversibly delete your save!
      </div>
      <div v-else>
        It's shortened because I know we'll both screw something up—very often at that too, no?
      </div>
    </div>
    <template #confirm-text>
      HARD RESET
    </template>
  </ModalWrapperChoice>
</template>
