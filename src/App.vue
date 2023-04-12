<script setup>
import { onMounted } from 'vue'
import { CapacitorHttp } from '@capacitor/core'

onMounted(async () => {

  await CapacitorHttp.post({
    url: 'https:/mydomain/api/authentication/login',
    headers: {
      "Content-Type": "application/json",
    },
    webFetchExtra: {
      credentials: "include",
    },
  }).then((response) => {
    alert(JSON.stringify(response.data));
  }).catch((error) => {
    alert(error.message);
  })

})
</script>

<template>
	hello world!
</template>

