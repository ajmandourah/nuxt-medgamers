<template>
<div>
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Home</nuxt-link></li>
        <li>How to</li>
        <li><nuxt-link to='/about'>About</nuxt-link></li>
      </ul>
    </nav>
  </header>
  <div class="container">
    <div class="row row-center">
      <div class="column">
        <nuxt />
      </div>
      <div class="column">
        <table>
          <tbody>
            <tr>
              <td valign="top" style="border-bottom: 0px">
                <div id="mum0"></div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  mounted() {
    // Use the process.browser to make sure that it loads on the browser side only.
    if (process.browser) {
      var mr = new mumbleReader(
        'https://ajmandourah.duckdns.org:21804/1?callback=?',
        'mum0'
      ) //init the object
      mr.settooltip(true) //to disable the tooltip change true to false
      mr.setuseservername(true) //Use the server name as name of the root channel
      mr.setlenght(50) //Set the max lenght for displaying or remove this line to have no limit
      mr.setimgpath('icons/') //Set the image path the local subdirectory MAKE SURE THAT U UPLOAD THE ICONS
      mr.setuseservername(true) //Do not show root in the Root channel but the given servername
      function load_mum() {
        mr.start() //This will reload the viewer
      }
      load_mum() //This will to the loading the first time
      window.setInterval(() => {
        load_mum()
      }, 30000) //This will load the viewer every 30 seconds
    }
  }
}
</script>

<style scoped>
.row,
.container{
  height: 100vh !important;
}
header{
  display: flex;
  justify-content: center;
}
nav{
  display: flex;
  position: absolute;
  justify-content: center;
  top: 0;
  margin-top: 25rem;
  width: 70%;
}
nav ul{
  margin: 0;
  padding: 0;
  margin: 0 auto;
  z-index: 99;
}
nav li{
  display: inline-block;
  text-align: center;
  margin-right: 15rem;
  text-transform: uppercase;
  letter-spacing: 0.5rem; 
}
nav a{
    color:rgb(96, 108, 118);
    text-decoration: none;

}

</style>
