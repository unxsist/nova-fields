<template>
  <div :class="wrapperClasses">
    <div
      v-if="!hideLabel"
      :class="labelClasses"
    >
      <slot>
        <form-label :for="field.name">
          {{ field.name || fieldName }}
        </form-label>

        <help-text :show-help-text="showHelpText">
          {{ field.helpText }}
        </help-text>
      </slot>
    </div>
    <div :class="fieldClasses">
      <slot name="field"/>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    wrapperClasses: {
      type: String,
      default: 'flex border-b border-40'
    },
    labelClasses: {
      type: String,
      default: 'w-1/5 px-8 py-6'
    },
    fieldClasses: {
      type: String,
      default: 'w-1/2 px-8 py-6'
    },
    hideLabel: {
      type: Boolean,
      default: false
    },
    field: {
      type: Object,
      required: true
    },
    fieldName: {
      type: String,
      default: ''
    },
    showHelpText: {
      type: Boolean,
      default: true
    }
  }
};
</script>
