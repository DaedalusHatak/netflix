<template>
<div class="tv">
    <div class="screen text"><h2>Enjoy on your TV</h2>
<p>Watch on Smart TVs, Playstation, Xbox, Chromecast, Apple TV, Blu-ray players, and more.</p></div>
<div class="screen"><img src="@/assets/tv.png" alt=""> <div class="video-screen"><video data-uia="nmhp-card-animation-asset-video" autoplay="true" playsinline="true" muted="true" loop="true"><source src="@/assets/video.mp4" type="video/mp4"></video></div>
</div>
   </div>
</template>

<style scoped>
.tv{
    height: 100%;
    min-height: auto;
    margin:auto;
    flex-wrap: nowrap;
    padding: 4.5rem 0;
    display: flex; 
    flex-direction: row;
    align-items: center;
}
h2{
    font-size: 3rem;
    font-weight: 900;
}
p{
    margin: 1rem 0 0;
}
.video-screen{

   
    overflow: hidden;
    width: 100%;
    height: 100%;
    max-width: 73%;
    max-height: 54%;
    position: absolute;
    top: 47.5%;
    left: 49.5%;
    transform: translate(-50%, -50%);
}
video{
    position: absolute;
    width: 100%;
}
img{
    z-index: 1;

    width: 100%;
}
.text{
    margin-bottom: 0.5rem;
}
.screen{
line-height: 1;
    position: relative;
    flex-basis: 50%;
}
</style>