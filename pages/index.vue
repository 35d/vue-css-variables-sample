<template>
  <div class="container" :style="styles">
    <div>
      <button @click="_onClickButton" class="button">ボタン</button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed, reactive } from '@vue/composition-api'

const urls = [
  'https://blog.35d.jp/img/glitched-01.png',
  'https://blog.35d.jp/img/glitched-02.png',
  'https://blog.35d.jp/img/glitched-03.png',
]

type State = {
  index: number
}

export default defineComponent({
  setup() {
    const state = reactive<State>({ index: 0 })
    const styles = computed<Object>(() => ({
      '--image-url': `url(${urls[state.index]})`,
    }))
    const _onClickButton = () => {
      state.index = (state.index + 1) % urls.length
    }

    return { _onClickButton, styles, state }
  },
})
</script>

<style>
.container {
  background-color: rgb(17, 17, 17);
  background-image: var(--image-url);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.button {
  cursor: pointer;
}
</style>
