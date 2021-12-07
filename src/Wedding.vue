<template>
  <div class="wedding">
    <Editor/>
    <audio
      id="cheerMusic"
      ref="audio"
      preload="auto"
      loop="loop"
      src="https://img.youpenglai.com/penglai/1.mp3"
    ></audio>
  </div>
</template>

<script>
  import Editor from "./components/Editor.vue"

  export default {
    props: [],
    components: {
      Editor
    },
    name: 'Wedding',
    async mounted () {
      this.audioAutoPlay()
    },
    methods: {
      audioAutoPlay() {
        let audio = this.$refs.audio
        audio.play();
        document.addEventListener("WeixinJSBridgeReady", function () {
          audio.play();
        }, false);
      },
    }
  }

</script>

<style lang="less">
@import './assets/base.less';
html,
body{
  height: 100%;
}
.wedding{
  position: relative;
  max-width: 568px!important;
  height: 100%;
  min-height: 100%;
  margin: 0 auto;
  background: #2B2B48;
  perspective: 500px;
}
</style>
