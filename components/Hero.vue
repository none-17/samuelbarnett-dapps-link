<template>
  <div
    id="hero"
    class="
      border-b-2
      px-4
      md:px-20
      py-20
      relative
      md:flex
      items-center
      justify-between
    "
  >
    <div class="text-part md:w-3/6">
      <h1 class="text-6xl font-bold md:w-11/12">
        Support Range for Decentralised Apps
      </h1>
      <p class="mt-8">Get instant cloud services for your development teams</p>
      <button class="mt-6">
        <a href="#function">Get Started</a>
      </button>
    </div>
    <img class="md:w-3/6 mt-5 md:mt-0" src="../static/IT-Support-.png" alt="" />
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
h1 {
  color: #1c280b;
}
button {
  background-color: rgb(0, 140, 115);
  color: rgb(247, 245, 245);
  box-shadow: rgb(212 212 211 / 59%) 1px 2px 10px 0px;
  display: inline-block;
  padding: 10px 20px;
  border-radius: 4px;
  font-weight: 800;
  letter-spacing: 0.4px;
  text-decoration: none;
  white-space: nowrap;
  transition: background-color 0.2s ease-in-out 0s, color 0.2s ease-in-out 0s;
}
</style>
