<template>
  <div class="container">
    <div>
      <Button :click="_onClickButton">ボタン</Button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

const urls = [
  'https://blog.35d.jp/img/glitched-01.png',
  'https://blog.35d.jp/img/glitched-02.png',
  'https://blog.35d.jp/img/glitched-03.png',
]

export default Vue.extend({
  methods: {
    _onClickButton() {},
  },
})
</script>

<style>
.container {
  background-color: rgb(17, 17, 17);
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
