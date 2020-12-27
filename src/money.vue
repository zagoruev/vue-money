<template>
  <component :is="tag">
    {{
      formatMoney(
        value,
        locale,
        currencyCode, {
          subunitsValue,
          subunitsToUnit,
          hideSubunits,
          supplementalPrecision
        }
      )
    }}
  </component>
</template>

<script>
  import formatMoney from './format-money'

  export default {
    props: {
      value: Number,
      tag: {
        type: String,
        default: 'div'
      },
      locale: {
        type: String,
        default: 'en'
      },
      currencyCode: {
        type: String,
        default: 'USD'
      },
      supplementalPrecision: {
        type: Number,
        default: 0
      },
      subunitsValue: {
        type: Boolean,
        default: false
      },
      subunitsToUnit: {
        type: Number,
        default: 1
      },
      hideSubunits: {
        type: Boolean,
        default: false
      }
    },
    methods: {
      formatMoney
    }
  }
</script>
