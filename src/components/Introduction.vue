<template>
  <div class="container">
    <div class="background">
      <div class="background_left"></div>
      <div class="me"></div>
      <div class="line_left"></div>

      <div class="background_right">
        <!-- <h1 class="title">Emiel Declercq</h1> -->

        <div class="text_background">
          <div class="intro">
            <p>
              Hey, welkom op mijn portfoliopagina hier zal u al mijn
              competenties en vaardigheden terugvinden, alsook mijn reeds
              gerealiseerde projecten. Ik heb me de laatste tijd voornamelijk
              gefocust op data analyse/artificial intelligence maar heb ook
              interesse in applicatieontwikkeling.
            </p>
            <p>
              Ik ben een leergierig persoon die op zoek is naar een job waar ik
              mijn technische vaardigheden kan toepassen en verder kan
              ontwikkelen op een maatschappelijke, mensgerichte manier, bij
              voorkeur in team waar duidelijke en vlotte communicatie een
              prioriteit is. Indien u op zoek bent naar iemand met deze
              vaardigheden kan u mijn contactgegevens
              <a href="#contact">hier</a> terugvinden.
            </p>
          </div>
        </div>
      </div>
      <div class="line_right"></div>
    </div>
  </div>
</template>

<script></script>

<style>
.title {
  color: black;
  margin-top: 30px;
  margin-bottom: 30px;
}

.intro {
  color: black;
}

.me {
  position: absolute;
  left: 363px;
  top: 200px;
  height: 350px;
  width: 350px;

  background: url(../me.jpg);
  background-size: 350px;

  border: 15px solid #000000;
  box-sizing: border-box;
  border-radius: 250px;
}

/* Rectangle 1 */

.text_background {
  position: absolute;
  width: 350px;
  height: 350px;
  left: 75px;
  top: 75px;

  background: rgba(164, 220, 234, 0.9);

  text-align: center;
}

.intro {
  padding: 20px;
  text-align: left;
}

p {
  margin-top: 0;
}
</style>
