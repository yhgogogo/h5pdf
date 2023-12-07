<template>
  <div class="home">
    <a href="/assets/pdfs/1.pdf" target="_blank">pdf 查看</a>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import QRCode from 'qrcode'
export default {
  name: 'HomeView',
  data(){
    return{
      src:'/',

    }
  },
  mounted(){
    this.makeQr()
  },
  methods:{
    makeQr(){
      console.log(this.src);
      QRCode.toDataURL(this.src)
      .then(url => {
        console.log(url)
        this.pdfurl=url
      })
      .catch(err => {
        console.error(err)
      })

    }
  }
}
</script>
