<template>
  <div>
    <h1>How to</h1>
    <h3>How to connect</h3>
    <p>
      Use this information to log in to the server through mumble.
      <br />Address
      <code>medgamers.duckdns.org</code> and the port is
      <code>21801</code> .
    </p>
    <h3>Backup server</h3>
    <p>
      In case of maintainance or problems ocurring in the current server, there is a backup server with limited features. Connect through
      <code>ladis.duckdns.org</code> and port
      <code>21801</code>.
    </p>
    <h3>MusicBOT</h3>
    <p>
      The music bot works by writing commands in the mumble chat. Use this code to play an audio file from youtube
      <code>!url [your YouTube link]</code>
    </p>
    <p>
      To stop the audio use
      <code>!stop</code>
    </p>
    <p>
      To show the help me menu use
      <code>!help</code>
    </p>

    <h3>Images in the chat</h3>
    <p>
      To post an image in the chat write
      <code>!img [the link to your image]</code>
    </p>

    <h3>User status</h3>
    <p>
      To set a new status message write
      <code>!set [your messege]</code> and to delete it use
      <code>!del</code>
    </p>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
h1 {
  font-family: 'Montserrat';
  font-weight: 600;
  text-align: left;

}
h3,
p {
  font-family: 'Montserrat';
}
h3 {
  font-weight: 400;
  margin-bottom: 10px;
}
p {
  font-weight: 400;
  line-height: 2.7rem;
}
</style>
