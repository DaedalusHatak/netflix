<script setup lang="ts">
import { ref } from 'vue'
const props = defineProps<{
  name: string
  type: string
}>()
const isActive = ref<boolean>(false)
const inputData = ref<string>('')
</script>

<template>
  <label :class="isActive ? 'label-active' : 'label'" for="emailfield">{{ props.name }}</label>
  <input
    :type="props.type"
    v-model="inputData"
    @focusout="inputData === '' ? (isActive = false) : (isActive = true)"
    @focusin="isActive = true"
    :is-active="isActive"
    autocomplete="email"
    id="emailfield"
    minlength="5"
    maxlength="50"
  />
</template>

<style scoped lang="scss">

input {
  color: white;
  padding: 1.5rem 1rem 0.5rem;
  border: none;
  border-radius: 1rem;
  font-size: inherit;

  min-height: 16px;
  min-width: 16px;
  width: 100%;
  background-clip: padding-box;
  appearance: none;
  background-color: transparent !important;

}

input:-webkit-autofill{
  transition: all 5s;
  -webkit-text-fill-color: white;
  -webkit-background-clip: text !important;
}

.label {
  position: absolute;
  z-index: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  transition-property: top, font-size, line-height;
  transition-duration: 250ms;
  pointer-events: none;
  font-size: 1rem;
  transition-timing-function: cubic-bezier(0.9, 0, 0.51, 1);
  color: rgba(255, 255, 255, 0.7);
  left: 1rem;
  line-height: 1.5rem;
  right: 1rem;
  top: 1rem;
}

.label-active {
  position: absolute;
  z-index: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  transition-property: top, font-size, line-height;
  transition-duration: 250ms;
  pointer-events: none;
  font-size: 0.75rem;
  transition-timing-function: cubic-bezier(0.5, 0, 0.1, 1);
  color: rgba(255, 255, 255, 0.7);
  left: 1rem;
  line-height: 1.125rem;
  right: 1rem;
  top: 0.5rem;
}
</style>
