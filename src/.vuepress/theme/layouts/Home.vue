<template>
  <div>
    <page-header />

    <article class="text container">
      <Content class="text" />
    </article>

    <div class="container text">
      <div class="telegram-invader clickable">
        Mit dem
        <a href="//t.me/joinchat/AAAAAE92NHpopjNHyCbXcA" target="_blank">
          JJBGF News
        </a>
        Kanal auf Telegram bleibst Du auf dem Laufenden.
      </div>

      <div
        class="info clickable text"
        style="background-image: radial-gradient(circle at 100%, #ffdd9c, #d6ffd0)"
      >
        <p><strong>Themenwunsch Umfrage</strong></p>
        <p>
          Es gibt ein Thema über welches Du dich mit anderen 
          austauschen möchtest, das dich bewegt oder eine 
          Frage, die Du schon immer stellen wolltest? 
          Dann notiere deinen
          <a
            style="background-color: #b1d2a9; font-weight: bold; white-space: nowrap;"
            href="https://docs.google.com/forms/d/e/1FAIpQLScycQh8Asn9wqHOmxSg2KG7Z6RjZidZqTq_fHkczVToxwO0FA/viewform"
            target="_blank"
          >
           Themenwunsch hier
          </a>

          <!-- <span style="font-weight: 500">
            Also wollen wir daran arbeiten und die Kommunikation verbessern.
          </span>
          Deshalb wäre es Klasse, wenn Du etwas Zeit für eine kurze -->
          <!-- <a
            style="background-color: #b1d2a9; font-weight: bold; white-space: nowrap;"
            href="https://docs.google.com/forms/d/e/1FAIpQLScycQh8Asn9wqHOmxSg2KG7Z6RjZidZqTq_fHkczVToxwO0FA/viewform"
            target="_blank"
          >
            Umfrage
          </a> -->
          <!-- hast. Danke ☺️ -->
        </p>
      </div>
    </div>

    <section class="container text foo">
      <header><h2>Sei dabei! 💫</h2></header>
      <teaser-event v-for="page in events" :key="page.key" :page="page" />
      <small-events />
    </section>

    <section class="container text foo">
      <header><h2>Events at home 🏡</h2></header>

      <div class="info clickable text">
        <p>
          ➡️ Dir ist langweilig und willst was unternehmen? Für Deine Ideen gibt
          es jetzt ein
          <a
            href="//docs.google.com/document/d/1L0EZC8gELYU3-iIPvnf-aeQCSEPJ_yVO35Xbc_p5hnQ/edit?usp=sharing"
            target="_blank"
          >
            Mitmach Docs
          </a>
        </p>
      </div>

      <!-- <div class="easter-invader clickable">
        🐰☎️ Vielen Dank für die vielen Nachrichten auf dem
        <strong>Osteranruf&shy;beantworter</strong>. Die nächste und letzte
        Übertragung des Zusammenschnitts gibt es am Sonnntag, den
        <strong>03.05.2020</strong>, nach den Abendgebeten.
      </div> -->

      <div class="info clickable text ">
        <p>
          🆕 Zusammen Block auf Block kreativ werden oder ein Abenteuer auf
          unserem neuen <strong>Minecraft Server</strong> erleben: Komm doch mal
          vorbei und sei dabei! 😉 <br />
          <small>Die Serveradresse bekommst du von deinen Jugendleitern</small>
        </p>
      </div>
    </section>

    <page-footer />
  </div>
</template>

<script>
import { ByDate, ByPriority, EventPages } from "../utils";

export default {
  computed: {
    events() {
      return EventPages(this.$site)
        .filter((page) => page.frontmatter.featured)
        .sort(ByDate("ASC"))
        .sort(ByPriority("DESC"));
    },
  },
};
</script>

<style lang="stylus">
.foo {
  margin-top:2rem;
}
</style>
