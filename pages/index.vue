<template>
<div>
          <h1>Medgamers <span>by Ladis</span></h1>
        <h3>A mumble channel online users viewer</h3>
        <p>Here you can view the online users in the mumble server. by hovering on the user's name you can see additional information like how long this user has been idle, and how long he/she has been online. <br>
        The interface refreshes every 30 seconds. You can manually refresh it by pressing the 'Refresh' button.
        </p>
</div>
</template>


<style scoped>
@import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,600&display=swap');
h1 {
  font-family: 'Montserrat';
  font-weight: 600;
  text-align: left;

}
h3 {
  font-family: 'Montserrat';
  font-weight: 300;
  text-align: left;
}
p{
  font-family: 'Montserrat';
  font-weight: 500;
  line-height: 2.5em;
  width: 80%;
}
span{
  color: #c0c6fc;
  font-weight: 400;
  font-size: 1.5rem;
}
@media (max-width: 40.0rem){
  h3{
    display: none;
  }
  h1{
    text-align: center;
  }
  p{
    display: none;
  }

}
</style>
