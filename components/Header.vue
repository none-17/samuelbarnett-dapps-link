<template>
  <div id="header">
      <header class="px-4 md:px-20">
          <a href="/">
              <img src="../static/dapp.png" width="50" height="50" alt="">
              <span class="">Wallet</span>
          </a>
          <nav>
              <ul>
                  <li class="hidden md:block">
                      <a href="/">Overview</a>
                  </li>
                  <li class="hidden md:block">
                      <a href="/">Swaps</a>
                  </li>
                  <li class="hidden md:block">
                      <a href="/">FAQs</a>
                  </li>
                  <button>
                      <a href="/#function">Connect</a>
                  </button>
              </ul>
          </nav>
      </header>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#header header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 55px;
    box-shadow: rgb(212 212 211 / 59%) 0px 2px 4px 0px;
    border-bottom: 2px solid rgb(232, 231, 230);
    background-color: cyan;
    overflow: hidden;
    
}


#header a {
    display: flex;
    align-items: center;
}

#header a span {
    font-size: 21px;
    font-weight: 900;
    letter-spacing: 0.4px;
    padding-left:4px ;
}

#header nav ul {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

#header nav ul li {
    font-weight: 800;
    letter-spacing: 0.4px;
}


#header nav ul li:not(:first-child) {
    margin-left: 50px;
}

#header nav ul button {
    margin-left: 40px;
    background-color: rgb(0, 140, 115);
    color: rgb(247, 245, 245);
    box-shadow: rgb(212 212 211 / 59%) 1px 2px 10px 0px;
    display: inline-block;
    padding: 6px 20px;
    border-radius: 8px;
    font-weight: 800;
    letter-spacing: 0.4px;
    text-decoration: none;
    white-space: nowrap;
    transition: background-color 0.2s ease-in-out 0s, color 0.2s ease-in-out 0s;
}

</style>