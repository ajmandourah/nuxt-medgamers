<template>
<div>
  <img class="bg" src="/bg.svg" alt="">
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Home</nuxt-link></li>
        <li><nuxt-link to='/howto'>How to</nuxt-link></li>
        <li><nuxt-link to='/about'>About</nuxt-link></li>
      </ul>
    </nav>
  </header>
  <div class="container">
    <div class="row">
      <div class="column content">
        <nuxt />
      </div>
      <div class="column mumble">
        <table>
          <tbody>
            <tr>
              <td valign="top" style="border-bottom: 0px">
                <div id="mum0"></div>
              </td>
            </tr>
          </tbody>
        </table>
        <div class="refresh" tooltip="Refresh the mumble interface" @click='refresh()'>Refresh</div>
      </div>
    </div>
  </div>
  <p id='mobile-text'>You are viewing the site in a mobile phone hence the simplified, strightforword view. To get the full experience check out the desktop version.</p>
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
      }, 50000) //This will load the viewer every 30 seconds

      //notification
      fetch('https://medapi.duckdns.org:3000/json', {
			mode: 'cors',
			headers: {'Content-Type': 'application/json'}
		})
		.then((resp) => resp.json())
		.then(msg => {
			msg = msg[0]
			var date = new Date(msg.created_at).toLocaleString()
			var notification = new Noty({
			text: '<b>' + msg.title + '</b>' + ' ' + date  + '<br>' +  msg.body,
			theme: 'nest',
			layout: 'bottomRight'
			});
			setTimeout( () => {
				notification.show()
				}, 500)
		})
    }
  },
  methods: {
    refresh: function() {
      var mr = new mumbleReader(
        'https://ajmandourah.duckdns.org:21804/1?callback=?',
        'mum0'
      )
      mr.start()
}
  }
}
</script>

<style>
.bg{ 
  position: fixed;
  top: 0;
  left: 0;
  width: 90vw;
}
body{
  background-color: #06102e;
}
h1, h3, p{
  color:white;
}

.container{
margin-top: 20vh;
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
  margin-top: 10vh;
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
    color:rgb(255, 255, 255);
    text-decoration: none;

}
nav a:hover{
  color: white;
}
nav a::before{
  content: '';
  display: block;
  position: relative;
  bottom: -3rem;
  left: -0.3rem;
  width:0%;
  height: 2px;
  opacity: 0;
  background-color: #eaeaff;
  transition: all cubic-bezier(1,-0.01, 0, 1.78) 0.4s;
}
nav a:hover::before{
  width: 100%;
  opacity: 1;
}

#mobile-text{
  display: none;
}
.refresh{
  width: 200px;
  height: 50px;
  background-color: #222e52;
      margin: auto;
    border-radius: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: rgba(255, 255, 255, 0.836);
    text-transform: uppercase;
    letter-spacing: 0.4rem;
      box-shadow: 5px 2px 30px 6px rgba(8, 3, 73, 0.664);
      font-family: 'Montserrat';
      cursor: pointer;

}

/* Mobile view */
@media (max-width: 40.0rem){
header{
  display: none;
}
.container{
margin-top: 5vh;
}
.mumble{
  margin-top: 5vh;
}
#mobile-text{
  display: block;
  text-align: center;
  width: 80vw;
  margin: 0 auto;
  margin-top: 2rem;
  color: rgba(255, 255, 255, 0.925);
}
.bg{ 
  display: none;
}
}

</style>
