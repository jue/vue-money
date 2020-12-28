<template>
  <el-input v-model="formatValue" v-bind="$attrs" />
</template>

<script>
export default {
  name: 'Money',
  model: {
    prop: 'value',
    event: 'update'
  },
  props: {
    value: {
      type: [String, Number],
      default: 0,
      desc: '金额数值'
    }
  },
  data () {
    return {
      formatValue: ''
    }
  },
  methods: {
    setFormatValue () {
      if (this.value != '') {
        this.formatValue = Number(this.value) / 100
      }
    }
  },
  watch: {
    value () {
      this.setFormatValue()
    },
    formatValue (newVal, oldVal) {
      if (newVal < 0) {
        this.formatValue = ''
      }
      this.formatValue = newVal.toString().match(/^\d*(\.?\d{0,2})/g)[0]
      if (newVal > 9999999999) {
        this.formatValue = oldVal
        return

      }
      this.$emit('update', this.formatValue * 100)
    }
  }
}
</script>
