<!-- eslint-disable vue/no-mutating-props -->
<template>
  <q-dialog v-model="dialog" ref="log">
    <q-card>
      <q-card-section class="row items-center">
        <q-avatar icon="signal_wifi_off" color="primary" text-color="white" />
        <span class="q-ml-sm"
          >You are currently not connected to any network.</span
        >
      </q-card-section>
      <q-card-actions align="right">
        <q-btn
          @click="$refs.log.hide()"
          flat
          label="Cancel"
          color="primary"
          v-bind="$attrs"
        />
        <!-- {{$refs.log}} -->
        <q-btn
          @click="
            $emit('accept');
            $refs.log.hide();
          "
          flat
          label="Turn on Wifi"
          color="primary"
          v-close-popup
        />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { computed, ref } from "vue";
const log = ref();
const dialog = ref(false);
console.log(log.value);
</script>
