<script setup lang="ts">
const ipcHandle = () => window.electron.ipcRenderer.send('ping')
</script>

<template>
  <button target="_blank" rel="noreferrer" @click="ipcHandle">Send IPC</button>
</template>
