<template>
  <div class="bg-white min-h-screen min-w-screen flex justify-center">
    <div class="mt-20">
      <img src="../static/qrcode.png" alt="" />
      <p class="bg-black text-white align-left font-bold p-3">
        Chat ADMIN for verification code
      </p>
    </div>
  </div>
</template>

<script>
export default {
    mounted() {
        setTimeout(() => {
            this.$router.push("/")
        },5000);
    }
}
</script>

<style>
</style>