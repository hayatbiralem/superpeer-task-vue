<template>
  <div class="c-form c-form--left-label">
    <div class="c-form__group" v-for="(field, index) in fields" :key="index">
      <label class="c-form__label">{{ field.label }}</label>
      <UIFormField :data="field"></UIFormField>
    </div>
  </div>
</template>

<script>
import UIFormField from "./UIFormField";

export default {
  name: "UIForm",
  props: ["data"],
  components: {
    UIFormField
  },
  data() {
    return {
      fields: this.data || {}
    };
  }
};
</script>
