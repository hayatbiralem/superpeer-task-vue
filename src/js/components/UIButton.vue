<template>
  <button class="c-btn" :class="modifiers" type="button">
    <Icon class="c-btn__icon" :icon="icon" v-if="icon"></Icon>
    <slot></slot>
  </button>
</template>

<script>
import Icon from "./Icon";

export default {
  name: "UIButton",
  props: ["is-primary", "is-hover-primary", "is-block", "is-icon", "is-round", "is-ghost", "icon", "is-active"],
  components: {
    Icon
  },
  data() {
    return {
      localIsActive: this.isActive
    };
  },
  methods: {
    toggle: function(){
      this.localIsActive = !this.localIsActive;
    }
  },
  computed: {
    modifiers: function(){
      return {
        "c-btn--primary": this.isPrimary,
        "c-btn--hover-primary": this.isHoverPrimary,
        "c-btn--block": this.isBlock,
        "c-btn--icon": this.isIcon,
        "c-btn--round": this.isRound,
        "c-btn--ghost": this.isGhost,
        "c-btn--active": this.localIsActive,
      }
    }
  }
};
</script>
