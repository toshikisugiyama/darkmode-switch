<template>
  <div
    class="button"
    @click="resetAll"
  >
    {{ buttonName }}
  </div>
</template>

<script>
export default {
  props: {
    buttonName: {
      type: String,
    },
  },
  methods: {
    resetAll(){
      this.$emit('reset-all')
    },
  },
}
</script>

<style lang="scss" scoped>
  .button {
    cursor: pointer;
    background-color: #727272;
    padding: 5px;
    border-radius: 5px;
    color: #fff;
    width: 80px;
    text-align: center;
    margin: 0 auto;
  }
  .container.dark {
    .button {
      background-color: #fff;
      color: #333;
    }
  }

</style>
