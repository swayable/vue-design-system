<template>
  <component
    :is='element'
    :class='["example", variation]'
  >
    <div id='Example-container'>
      <slot />
    </div>
  </component>
</template>

<script>
/**
 * Example component is used to visually communicate core parts of the product
 * and available actions.
 */
export default {
  /**
   * Component names should be short, pronounceable and Capitalized.
   */
  name: 'Example',
  /**
   * Components in the system are labelled with status labels that reflect their
   * state of completion. See example below. All available statuses are:
   *
   * STATUS:        COLOR:     DESCRIPTION:
   *
   * deprecated     Red        Component is deprecated
   * prototype      Blue       Prototype, do not implement!
   * review         Yellow     Component is currently being reviewed
   * ready          Green      Ready to be used
   */
  status: 'prototype',
  /**
   * Prop definitions should be as detailed as possible, specifying at least
   * type(s). See examples below:
   */
  props: {
    /**
     * The html element name used for the container of Example component.
     */
    element: {
      type: String,
      default: 'div',
    },
    /**
     * Style variation to give additional meaning.
     * `default, strong, positive, negative`
     */
    variation: {
      type: String,
      default: 'default',
      validator: value => {
        return value.match(/(default|strong|positive|negative)/)
      },
    },
  },
}
</script>

<docs>
  ```jsx
  <Example>
    Docs section should have an example that is shown in the documentation.
  </Example>
  ```
</docs>
