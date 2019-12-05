<template>
  <li class="list-item">
    {{ message }}
    <div
      @click="toggle"
      class="frame"
      :class="{ 'frame-on' : isOn }"
    >
      <div class="button"></div>
    </div>
  </li>
</template>

<script>
export default {
  props: {
      message: {
        type: String,
      },
      isOn: {
        type: Boolean,
        default: false,
      },
  },
  methods: {
    toggle(){
      this.$emit('toggle-switch', !this.isOn)
    },
  },
}
</script>

<style lang="scss" scoped>
.list-item {
  margin: 10px auto;
  display: flex;
  align-items: center;
  .frame {
    background-color: #333;
    width: 70px;
    height: 30px;
    border-radius: 100px;
    padding: 3px;
    box-sizing: border-box;
    margin: 0 0 0 auto;
    cursor: pointer;
    transition: all 0.3s;
    .button {
      background-color: #fff;
      width: 24px;
      height: 24px;
      border-radius: 50%;
      display: inline-block;
    }
  }
  .frame.frame-on {
    background-color: greenyellow;
    text-align: right;
  }
}
.container.dark {
  .list-item {
    .frame {
      background-color: #fff;
      .button {
        background-color: #333;
      }
    }
    .frame.frame-on {
      background-color: greenyellow;
    }
  }
}
</style>
