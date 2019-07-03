<template>
    <div>
        <h3>MusicBOT</h3>
        <p>The music bot works by writing commands in the mumble chat. Use this code to play an audio file from youtube <code>!url [your YouTube link]</code></p>
        <p>To stop the audio use <code>!stop</code></p>
        <p>To show the help me menu use <code>!help</code></p>
        <hr>
        <h3>Images in the chat</h3>
        <p>To post an image in the chat write <code>!img [the link to your image]</code></p>
        <hr>
        <h3>User status</h3>
        <p>To set a new status message write <code>!set [your messege]</code> and to delete it use <code>!del</code></p>
        <hr>


    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
h3, p{
    font-family: 'Montserrat';
}
h3{
    font-weight: 400;
}
p{
    font-weight: 400;
}
</style>
