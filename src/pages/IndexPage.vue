<template>
  <div>test</div>
  <DialogSample @accept="logger"></DialogSample>
</template>

<script setup>
import { ref } from "vue";
import DialogSample from "src/components/DialogSample.vue";
const toggle = ref(true);
function logger() {
  console.log("check");
  toggle.value = !toggle.value;
}
</script>
