<template>
  <div id="qr-code-full-region"></div>
  <div>{{this.result}}</div>
<!--  <button>-->
<!--    <i class="fa-regular fa-folder"></i>-->
<!--  </button>-->
</template>

<script>
import {Html5QrcodeScanner} from "html5-qrcode"

export default {
  name: "qrcode",
  data() {
    return {
      // qrbox: {
      //   type: Number,
      //   default: 250
      // },
      // fps: {
      //   type: Number,
      //   default: 10
      // },
      result: null,
    }
  },
  mounted() {
    const html5QrcodeScanner = new Html5QrcodeScanner('qr-code-full-region', {fps: 10, qrbox: {width: 250, height: 250}});
    html5QrcodeScanner.render(this.onScanSuccess,  this.onScanFailure);
  },
  methods: {
    onScanSuccess (decodedText, decodedResult) {
      console.log(decodedText)
      this.result = decodedText
    },
    // onScanSuccess(decodedText, decodedResult) {
    //   // handle the scanned code as you like, for example:
    //   console.log(`Code matched = ${decodedText}`, decodedResult);
    // },
    onScanFailure(error) {
      // handle scan failure, usually better to ignore and keep scanning.
      // for example:.
      console.warn(`Code scan error = ${error}`);
    },
  },
}
</script>

<style scoped>
i {
  color: rgb(245, 245, 245);
  font-size: 2.3rem;
}
button {
  position: absolute;
  right: 2%;
  bottom: 3%;
  background-color: #198754;
  padding: 0.5rem;
  width: 4rem;
  height: 4rem;
  border-radius: 50%;
  border: none;
  box-sizing: border-box;
}
button:active {
  background-color: rgb(245, 245, 245);
}
button:active i {
  color: #198754;
}
</style>