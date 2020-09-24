<template>
  <div :class="'c-form__field c-form__field--' + type + (leftIcon ? ' c-form__field--icon-left' : '') + stateClasses">
    <Icon
      class="c-form__icon c-form__icon--left"
      :icon="leftIcon"
      width="24"
      height="24"
      v-if="leftIcon"
    ></Icon>

    <input
      class="c-form__input c-form__input--text"
      :class="stateClasses"
      type="text"
      v-model="value"
      v-if="type === 'text'"
      :disabled="disabled"
    />

    <select
      class="c-form__input c-form__input--select"
      v-if="type === 'select' && options"
      v-model="value"
      :disabled="disabled"
    >
      <option
        v-for="(option, index) in options"
        :key="index"
        :value="option.value"
      >
        {{ option.text }}
      </option>
    </select>

    <UIButton :is-primary="1" :is-ghost="1" :is-block="1" @click.native="on.click" v-if="type == 'button'" :disabled="disabled">
      {{ text }}
    </UIButton>

    <Icon icon="fill-arrow-down" class="c-form__caret" width="18" height="18" v-if="type === 'select'"></Icon>

    <span class="c-form__input-base" aria-hidden="true"></span>
  </div>
</template>

<script>
import Icon from "./Icon";
import UIButton from "./UIButton";

export default {
  name: "UIFormField",
  props: ["data"],
  components: {
    Icon,
    UIButton,
  },
  data() {
    return {
      name: this.data.name,
      type: this.data.type,
      value: this.data.value,
      leftIcon: this.data.leftIcon,
      options: this.data.options,
      text: this.data.text,
      on: this.data.on,
      disabled: this.data.disabled,
      success: this.data.success,
      error: this.data.error,
    };
  },
  computed: {
    stateClasses: function(){
      return (this.success ? ' c-form__field--success' : '') + (this.error ? ' c-form__field--error' : '') + (this.disabled ? ' c-form__field--disabled' : '');
    }
  }
};
</script>
