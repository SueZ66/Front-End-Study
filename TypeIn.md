## TypeIn

打字输入效果的实现

```vue
<template>
  <div>
    <h1  :style="styleVariable">{{content}}</h1>
  </div>
</template>

<script>
export default {
  props: ['content'],
  data() {
    return {
      length: this.content.length
    }
  },
  computed: {
    styleVariable() {
      return {
        '--text-length': this.length,
        '--text-width': (this.length * 2) + 'ch',
        '--animation-time': (this.length / 4) + 's',
      }
    }
  },
}
</script>

<style lang="scss" scoped>
h1 {
  $length: var(--text-length);
  $width: var(--text-width);
  $time: var(--animation-time);
  font: bold 200% monospace;
  border-right: 0.1em solid;
  width: $width;
  white-space: nowrap;
  overflow: hidden;
  animation: typing $time steps($length, end),
             cursor-blink 0.5s step-end infinite alternate;
}

@keyframes typing {
  from {
    width: 0;
  }
}

@keyframes cursor-blink {
  50% {
    border-color: transparent;
  }
}

</style>

```

