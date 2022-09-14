<template>
  <img class="bg-image" alt="lila." src="./assets/bg_image.jpg">
  <div class="container">
    <div class="title">
      <h1>Warum heisst es Lila?</h1>
    </div>
    <div class="text-block">
      Wegen einem Schlager-Hit aus dem Jahr 1920! Das «Lila Lied» war ein echter Gassenhauer. Der Ohrwurm packte den Stolz, queer zu sein, das erste Mal in Noten. Die lesbische und schwule Community haute damals – zwischen zwei Weltkriegen – das erste Mal so richtig auf den Putz. Wir wollten uns nicht mehr im Schrank verstecken.<br>
      Mithilfe des Schlagers wurden für damalige Verhältnisse verwegene und anstössige Homo-Themen angepackt. Das «Lila Lied» mit der Musik von Mischa Spoliansky und dem eindeutigen Text von Kurt Schwabach war etwas völlig Neues. Der Song brachte ein neues Selbstbewusstsein zum Ausdruck.<br>
      Der Traum von einer neuen Zeit, in der laut Song-Text «das gleiche Recht erstritten» ist und Homosexuelle nicht mehr leiden, sondern «(wohl)gelitten» (akzeptiert) sind, habe queere Menschen damals tief berührt. Der Foxtrott mit seinem eindeutigen Text hat den Stolz besungen: «Wir lieben nur die lila Nacht, die schwül ist, weil wir ja anders als die andern sind.»<br>
      <i>Quelle: Birgit Kawohl und Mark Baer, Cruiser Magazin</i>
    </div>

    <div class="audio-player-container">
      <audio-player
          ref="audioPlayer"
          :audio-list="[lilaLied.url]"
          theme-color="#000"
          :show-playback-rate="false"
          :show-volume-button="false"
          :show-prev-button="false"
          :show-next-button="false"
      />
    </div>

  </div>
</template>

<script lang="ts" setup>
import AudioPlayer from '@liripeng/vue-audio-player'

const lilaLied = {
  url: '/lila_lied.mp3',
}
</script>

<style lang="scss">
html {
  background: black;
}

#app {
  font-family: 'Source Sans Pro', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
}

.bg-image {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.container {
  z-index: 1;

  h1 {
    font-size: 54px;
    line-height: 95%;
    text-transform: uppercase;
    margin: 0;
    font-weight: 900;
  }

  .title {
    position: absolute;
    top: 48px;
    left: 24px;
    width: 450px;
  }

  .text-block {
    background: white;
    padding: 16px;
    margin-top: 240px;
    width: 75%;
    margin-left: 18%;
    font-weight: 600;
    line-height: 150%;
  }

  .audio-player-container {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background: white;
    padding: 16px 32px;
  }
}
</style>
