<template>
  <div ref="testRef" id="test">
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue';
// @ts-ignore
import { init, on } from 'ys-webrtc-sdk-ui';
import 'ys-webrtc-sdk-ui/lib/ys-webrtc-sdk-ui.css';
const testRef = ref(null);
onMounted(()=>{
  if (testRef.value) {
    init(testRef.value, {
      pbxURL: 'https://your-pbx.com',
      secret: '',
      username: '1000',
    }).then(()=>{
      console.log('init success')
    })
  }
});
</script>