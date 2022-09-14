<template>
  <img alt="lila." class="bg-image" src="./assets/bg_image.jpg">
  <div class="container">
    <div class="title">
      <h1>Warum heisst es Lila?</h1>
    </div>
    <div class="text-block">
      Wegen einem Schlager-Hit aus dem Jahr 1920! Das «Lila Lied» war ein echter Gassenhauer. Der Ohrwurm packte den
      Stolz, queer zu sein, das erste Mal in Noten. Die lesbische und schwule Community haute damals – zwischen zwei
      Weltkriegen – das erste Mal so richtig auf den Putz. Wir wollten uns nicht mehr im Schrank verstecken.<br>
      Mithilfe des Schlagers wurden für damalige Verhältnisse verwegene und anstössige Homo-Themen angepackt. Das «Lila
      Lied» mit der Musik von Mischa Spoliansky und dem eindeutigen Text von Kurt Schwabach war etwas völlig Neues. Der
      Song brachte ein neues Selbstbewusstsein zum Ausdruck.<br>
      Der Traum von einer neuen Zeit, in der laut Song-Text «das gleiche Recht erstritten» ist und Homosexuelle nicht
      mehr leiden, sondern «(wohl)gelitten» (akzeptiert) sind, habe queere Menschen damals tief berührt. Der Foxtrott
      mit seinem eindeutigen Text hat den Stolz besungen: «Wir lieben nur die lila Nacht, die schwül ist, weil wir ja
      anders als die andern sind.»<br>
      <i>Quelle: Birgit Kawohl und Mark Baer, Cruiser Magazin</i>
    </div>

    <div class="audio-player-container">
      <div class="text-line">
        <span>Das Lila Lied - Ute Lemper</span>
        <button
            @click="showSongtext = !showSongtext"
        >{{ showSongtext ? 'SCHLIESSEN' : 'SONGTEXT'}}</button>
      </div>
      <audio-player
          ref="audioPlayer"
          :audio-list="[lilaLied.url]"
          :show-next-button="false"
          :show-playback-rate="false"
          :show-prev-button="false"
          :show-volume-button="false"
          theme-color="#000"
      />
    </div>
    <div class="songtext" :class="{ 'show': showSongtext }">
      <h2 style="margin: 0">DAS LILA LIED</h2><br>
      <br>
      Was will man nur? Ist das Kultur,<br>
      Daß jeder Mensch verpönt ist,<br>
      Der klug und gut, jedoch mit Blut<br>
      Von eigner Art durchströmt ist,<br>
      Daß grade die Kategorie<br>
      Vor dem Gesetz verbannt ist,<br>
      Die im Gefühl bei Lust und Spiel<br>
      Und in der Art verwandt ist?<br>
      Und dennoch sind die meisten stolz,<br>
      Daß sie von anderm Holz!<br>
      <br>
      <br>
      Wir sind nun einmal anders, als die andern,<br>
      Die nur im Gleichschritt der Moral geliebt,<br>
      Neugierig erst durch tausend Wunder wandern,<br>
      Und für die ′s doch nur das Banale gibt.<br>
      Wir aber wissen nicht, wie das Gefühl ist,<br>
      Denn wir sind alle andrer Welten Kind;<br>
      Wir lieben nur die lila Nacht, die schwül ist,<br>
      Weil wir ja anders als die andern sind.<br>
      <br>
      Wozu die Qual, uns die Moral<br>
      Der andern aufzudrängen?<br>
      Wir, hört geschwind, sind wie wir sind,<br>
      Selbst wollte man uns hängen.<br>
      Wer aber denkt, daß man uns hängt,<br>
      Den müßte man beweinen,<br>
      Doch bald gebt acht, es wird über Nacht<br>
      Auch unsre Sonne scheinen.<br>
      Dann haben wir das gleiche Recht erstritten,<br>
      Wir leiden nicht mehr, sondern sind gelitten.<br>
    </div>
  </div>
</template>

<script lang="ts" setup>
import AudioPlayer from '@liripeng/vue-audio-player'
import {ref} from "vue";

const showSongtext = ref(false);

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
  font-weight: 600;
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

  button {
    border: none;
    background: transparent;
    font-weight: 900;
    padding: 0;
    font-size: 16px;
  }

  .text-line {
    display: flex;
    justify-content: space-between;
    align-items: center;
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
    z-index: 2;
  }

  .songtext {
    position: fixed;
    background: white;
    padding-top: 50px;
    left: 0;
    right: 0;
    top: 0;
    height: 800px;
    text-align: center;
    font-weight: 600;
    line-height: 140%;
    transform: translateY(100vh);
    transition: all 0.5s ease-in-out;
    overflow: scroll;

    &.show {
      transform: translateY(0);
    }
  }
}
</style>
