<template>
  <div>test</div>
  <DialogSample @accept="logger"></DialogSample>
  <q-input
    :error="hasError"
    :error-message="errorMeessage"
    outlined
    v-model="text"
    label="Outlined"
  />
  {{ text }}
</template>

<script setup>
import { ref } from "vue";
import DialogSample from "src/components/DialogSample.vue";
import { watch } from "fs";
const toggle = ref(true);
const text = ref("");
const hasError = ref(false);
const errorMeessage = ref("");
function logger() {
  console.log("check");
  toggle.value = !toggle.value;
}

watch(text, async (newtext, oldText) => {
  if (newtext.length > 5) {
    hasError.value = true;
    errorMeessage.value = "content should be less than 5 charachter";
  }
});
</script>
