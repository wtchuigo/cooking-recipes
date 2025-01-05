<template>
  <div id="footer">
    <hr />
    <div id="logo">
      <a href=""><img src="../images/linkedin.png" /></a>
      <a href=""><img src="../images/Logo-Instagram-noir-1.webp" /></a>
      <a href=""><img src="../images/logo-twitter-noir.png" /></a>
    </div>
    <div id="contact">
      <a href="tel:+4972297861648">Telephone</a>
      <a href="mailto:william.tchuigoua@gmail.com">E-Mail</a>
    </div>
  </div>
</template>

<script>
</script>

<style scoped>
#footer {
  position: fixed;
  background: #e5ba73;
  height: 10%;
  display: flex;
  left: 0;
  bottom: 0;
  width: 100%;
  justify-content: center;
  flex-direction: column;
}

#footer img {
  width: 20px;
  height: 20px;
  margin-right: 1em;
}

#logo {
  display: flex;
  justify-content: center;
  margin-top: 1em;
}

#contact {
  display: flex;
  justify-content: center;
}

#contact a {
  margin-top: 1em;
  margin-right: 1em;
  color: black;
  padding: 0.5em;
}

#contact:hover a {
  color: white;
  background-color: #c58940;
  border-radius: 3em;
}
</style>