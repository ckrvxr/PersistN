<script setup lang="ts">
const ipcHandle = () => window.electron.ipcRenderer.send('ping')
import './assets/main.css'

import { ref } from 'vue'

const drawer = ref(true)
</script>

<template>
  <v-layout>
    <v-navigation-drawer v-model="drawer" floating permanent>
      <v-list density="comfortable">
        <v-list-item class="ma-2" link nav title="Dashboard" />
        <v-list-item class="ma-2" link nav title="Statistics" />
        <v-list-item class="ma-2" link nav title="Devices" />
        <v-list-item class="ma-2" link nav title="Settings" />
        <v-list-item class="ma-2" link nav title="Account" />
        <v-btn @click="ipcHandle"> Send IPC </v-btn>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar border="b" class="ps-4" flat>
      <v-app-bar-title>Dashboard</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <div class="pa-4">
        <v-sheet border="dashed md" color="surface-light" height="500" rounded="lg" width="100%" />
      </div>
    </v-main>
  </v-layout>
</template>
