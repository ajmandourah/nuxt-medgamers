<template>
    <div>
          <h1>About</h1>
        <h3>Here you can view the connected users in the mumble server.</h3>
        <p>This page is created by Ladis using <span>Nuxt, Vue and the mumbleReader script</span> to fetch the online users information. Its open sourced and you can find the 
          source code on <a href='https://github.com/ajmandourah/nuxt-medgamers'>Github</a>. Enjoy!.
        </p>
</div>
</template>

<script>
export default {

}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,600&display=swap');
h1, p {
  font-family: 'Montserrat';
  font-weight: 400;
  text-align: left;

}
h3 {
  font-family: 'Montserrat';
  font-weight: 300;
    text-align: left;

}
span{
  color: #bfc9ff;
  font-weight: 600;
}

</style>
