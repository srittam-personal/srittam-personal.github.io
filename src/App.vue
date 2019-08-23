<template>
  <div class="app">
    <div class="free-shipping">FREE US SHIPPING & RETURN</div>
    <Header/>
    <router-view/>
    <Footer/>
  </div>
</template>

<script>
  import Header from "./components/header/Header.vue";
  import Footer from "./components/footer/Footer.vue";

  export default {
    components:{
      Header,
      Footer
    }
  }
</script>

<style lang="scss">

  @font-face {
    font-family: 'Gotham-bold';
    src: url('./assets/fonts/Gotham-Bold.eot'); /* IE9 Compat Modes */
    src: url('./assets/fonts/Gotham-Bold.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('./assets/fonts/Gotham-Bold.woff') format('woff'), /* Pretty Modern Browsers */
        url('./assets/fonts/Gotham-Bold.ttf')  format('truetype'), /* Safari, Android, iOS */
        url('./assets/fonts/Gotham-Bold.svg#svgFontName') format('svg'); /* Legacy iOS */
  }

  @font-face {
    font-family: 'Gotham-Medium';
    src: url('./assets/fonts/Gotham-Medium.eot'); /* IE9 Compat Modes */
    src: url('./assets/fonts/Gotham-Medium.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('./assets/fonts/Gotham-Medium.woff') format('woff'), /* Pretty Modern Browsers */
        url('./assets/fonts/Gotham-Medium.ttf')  format('truetype'), /* Safari, Android, iOS */
        url('./assets/fonts/Gotham-Medium.svg#svgFontName') format('svg'); /* Legacy iOS */
  }

  @font-face {
    font-family: 'GothamHTF-Book';
    src: url('./assets/fonts/GothamHTF-Book.eot'); /* IE9 Compat Modes */
    src: url('./assets/fonts/GothamHTF-Book.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
        url('./assets/fonts/GothamHTF-Book.woff') format('woff'), /* Pretty Modern Browsers */
        url('./assets/fonts/GothamHTF-Book.ttf')  format('truetype'), /* Safari, Android, iOS */
        url('./assets/fonts/GothamHTF-Book.svg#svgFontName') format('svg'); /* Legacy iOS */
  }

  $color-black : #000000;
  $color-white : #ffffff;


  * {
    text-rendering: optimizeLegibility;
    -moz-osx-font-smoothing: grayscale;
    font-smoothing: antialiased;
    -webkit-font-smoothing: antialiased;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
  html, body {
    height: 100%;
  }
  body {
    color: #363636;
    font-family: 'Arimo','Helvetica Neue',Helvetica,Arial,sans-serif;
    font-style: normal;
    font-weight: 400;
    line-height: 1;
    font-size: 1.4rem;
    margin: 0;
    padding: 0;
    background-color: #fff;
  }
  ul,li {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  a {
    color: #000;
    text-decoration: none;
  }
  img{
    max-width: 100%;
  }

  .container {
    max-width: 1380px;
    margin: 0 auto;
    padding: 0 20px;
  }
  .free-shipping {
    background: $color-black ;
    text-align: center;
    color: $color-white;
    font-size: 12px;
    text-transform: uppercase;
    padding: 10px 0;
    font-family: 'GothamHTF-Book';
    letter-spacing: 0.075rem;
  }
</style>
