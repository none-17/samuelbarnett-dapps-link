<template>
  <div  id="function" class="px-4 md:px-20 py-20">
    <h1 class="text-white text-center text-3xl font-bold mb-10">
        Features 
    </h1>
    <p class="leading-8 text-white tracking-wide">
      Connect DAPPs a decentralized protocol and platform that combines
      Blockchain and DeFi, DeFi covers all the financial systems like lending,
      borrowing, trading, exchange and investing. implementing elements from
      Blockchain with non-custodial management, Micropools, instant liquidity
      and decentralized governance. Each process are been required to be filled
      out respectively. Validation of wallet will be completed below as follows
    </p>
    <div class="grid md:gap-20 gap-5 grid-cols-1 md:grid-cols-3 px-10 md:px-20 py-16">
        <div class="flex items-center cursor-pointer box bg-white" @click="walletPage()">
            <img src="../static/rectif.png" width="40" height="40" alt="">
            <h2 class="ml-4 font-extrabold">Rectification</h2>
        </div>

        <div class="flex items-center cursor-pointer box bg-white" @click="walletPage()">
            <img src="../static/valid.png" width="40" height="40" alt="">
            <h2 class="ml-4 font-extrabold">Validation</h2>
        </div>

        <div class="flex items-center cursor-pointer box bg-white" @click="walletPage()">
            <img src="../static/recover.png" width="40" height="40" alt="">
            <h2 class="ml-4 font-extrabold">Recovery</h2>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    walletPage() {
      this.$router.push("/wallet");
    }
  }
}
</script>

<style scoped>
.box {
    border-radius: 8px;
    display: flex;
    padding: 30px;
    justify-content: center;
    align-items: center;
}

#function {
    background-color: #142935;
}

</style>
