<template>
  <div
    id="index"
    class="container"
  >
    <CreateArea
      v-model="input"
      @click="download()"
    />
    <GenerateContent :text="input" />
    <a
      id="download"
      ref="download"
      href="#"
      style="display:none;"
      download="canvas.jpg"
    >ダウンロード</a>
  </div>
</template>

<script>
import CreateArea from '@/components/Organisms/CreateArea.vue'
import GenerateContent from '@/components/Organisms/GenerateContent.vue'
import html2canvas from 'html2canvas'
export default {
  components: {
    CreateArea,
    GenerateContent
  },
  data() {
    return {
      input: 'Uber'
    }
  },
  methods: {
    download() {
      html2canvas(document.getElementById('target-logo')).then((canvas) => {
        let ctx = canvas.getContext('2d')
        let base64 = canvas.toDataURL('image/jpeg')
        document.getElementById('download').href = base64
        let img = new Image()
        img.src = 'image.jpg'
        ctx.drawImage(img, 0, 0)
        this.$refs.download.click()
      })
    }
  }
}
</script>

<style lang="scss" scoped>
#index {
  padding: 24px;
}
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
