<template>
  <div>test</div>
  <DialogSample @accept="logger"></DialogSample>
  <q-input outlined v-model="text" label="Outlined" />
  {{ text }}
</template>

<script setup>
import { ref } from "vue";
import DialogSample from "src/components/DialogSample.vue";
const toggle = ref(true);
const text = ref("");
function logger() {
  console.log("check");
  toggle.value = !toggle.value;
}
</script>
