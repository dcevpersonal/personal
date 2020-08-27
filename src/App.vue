<template>
  <div id="app">
    <Base />
  </div>
</template>

<script>

import Base from "./components/Base/Base";

export default {
  name: 'App',
  components: {
    Base
  }
}

</script>

<style>


@font-face {
  font-family: Gilroy;
  src: url("./assets/Fonts/Gilroy.otf");
}


@font-face {
  font-family: Gilroy_Light;
  src: url("./assets/Fonts/Gilroy-Light.otf");
}


@font-face {
  font-family: Roboto;
  src: url("./assets/Fonts/Roboto.ttf");
}


html,body {
  width: 100%;
  height: 100%;
  color: #262525;
  margin: 0;
  padding: 0;
}


h1,h2,p,a {
  padding: 0;
  margin: 0;
}


#app {
  widows: 100%;
  height: 100%;
}


@media only screen and (max-width: 1100px) {
    html,body {
    width: 100%;
    height: 100%;
}


}

</style>
