<template>
  <div class="import flex items-center justify-center mt-20">
    <!-- <a href="/">Import Wallet</a> -->
    <div class="import-container w-full md:w-auto">
      <div class="ps-content md:p-5 md:max-w-md bg-gray-100 shadow border">
        <el-tabs type="border-card box">
          <el-tab-pane label="MNEMONIC">
            <Mnemonic :wallet-type="walletType" />
          </el-tab-pane>
          <el-tab-pane label="KEYSTORE">
            <Keystore :wallet-type="walletType" />
          </el-tab-pane>
          <el-tab-pane label="PRIVATE KEY">
            <Private :wallet-type="walletType"/>
          </el-tab-pane>
          <el-tab-pane label="HARDWARE">
            <Private :wallet-type="walletType" />
          </el-tab-pane>
        </el-tabs>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            walletType: ''
        }
    },
    mounted() {
        this.walletType = this.$route.params.wallet;
    }
}
</script>

<style>

.el-tabs__item:hover, .el-tabs__item.is-active {
    color: rgb(0, 140, 115) !important;
}

.el-textarea__inner:focus {
    border-color: rgb(0, 140, 115) !important;
}

.el-input.is-active .el-input__inner, .el-input__inner:focus {
    border-color: rgb(0, 140, 115) !important;
}

</style>
