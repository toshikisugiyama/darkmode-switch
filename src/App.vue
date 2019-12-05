<template>
  <div
    class="container"
    :class="{dark: darkMode.isOn}"
  >
    <div class="box">
      <ul class="switch-list">
        <ToggleSwitch
          :message="notice.message"
          :is-on="notice.isOn"
          @toggle-switch="notice.isOn=$event"
        />
        <ToggleSwitch
          :message="searchFilter.message"
          :is-on="searchFilter.isOn"
          @toggle-switch="searchFilter.isOn=$event"
        />
        <ToggleSwitch
          :message="darkMode.message"
          :is-on="darkMode.isOn"
          @toggle-switch="darkMode.isOn=$event"
        />
      </ul>
      <Reset
        :button-name="reset.buttonName"
        @reset-all="resetAll"
      />
    </div>
  </div>
</template>

<script>
import ToggleSwitch from './components/ToggleSwitch.vue'
import Reset from './components/Reset.vue'
export default {
  components: {
    ToggleSwitch,
    Reset,
  },
  data(){
    return {
      notice: {
        message: '通知',
        isOn: false,
      },
      searchFilter: {
        message: '検索フィルター',
        isOn: false,
      },
      darkMode: {
        message: 'ダークモード',
        isOn: false,
      },
      reset: {
        buttonName: 'リセット',
      }
    }
  },
  methods: {
    resetAll() {
      this.notice.isOn = false
      this.searchFilter.isOn = false
      this.darkMode.isOn = false
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    height: 100vh;
    width: 100vw;
    padding: 100px 0;
    box-sizing: border-box;
    .box {
      border: 2px #333 solid;
      border-radius: 10px;
      padding: 50px;
      width: 300px;
      margin: auto;
      .switch-list {
        padding: 0;
      }
    }
  }
  .container.dark {
    background-color: #333;
    color: #fff;
    .box {
      border: #fff solid 2px;
    }
  }
</style>
