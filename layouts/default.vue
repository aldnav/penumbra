<template>
  <v-container
    fluid>
    <v-layout
      row
      wrap>
      <v-flex md2/>
      <v-flex md4>
        <header>
          <h3>Ventures of the</h3>
          <h1>Penumbra</h1>
          <h1>Mafia</h1>
          <hr>
        </header>
        <section id="section-1">
          <h2>Meet the Dons who run Silicon Valley – the PayPal Mafia.</h2>
          <p>Despite the name, this ‘outfit’ is an entirely legit group of tech entrepreneurs - the founders and former employees of PayPal. The ‘Mafia’ have continued to work and invest together since the company’s 2002 sale to eBay. Between them, they’ve founded, funded or led some of the world’s biggest tech firms</p>
        </section>
        <section id="section-2">
          <h2>Household names</h2>
          <p>Besides PayPal, the Mafia are connected to many other notable brands. Steve Chen, Chad Hurley and Jawed Karim worked at PayPal before they founded YouTube in 2005. Yelp and LinkedIn were also started by PayPal Mafiosi.</p>
        </section>
        <section id="section-3">
          <h2>Fingers in every pie</h2>
          <p>Although most of the PayPal Mafia’s investments have stayed within their traditional territory of Silicon Valley tech, more unusual Family ventures have included private spaceflight company SpaceX, Hollywood movie Thank You for Smoking and political campaign group FWD.us.</p>
        </section>
        <section id="section-4">
          <h2>Follow the money</h2>
          <p>In addition to exec roles and individual investments in over 400 companies, several of these Bosses have started and contributed to some of Silicon Valley’s biggest investment funds, giving them a piece of the action in thousands more.</p>
        </section>
        <section id="section-5">
          <h2>Capisce? Now investigate the connections for yourself</h2>
          <p>Explore the visualisation to see the many companies the PayPal Mafia are involved in, and find out which well-known brands they helped shape. See how the Mafiosi remain connected through numerous joint ventures in Silicon Valley and beyond.</p>
        </section>
      </v-flex>
      <v-flex md6>
        visualization
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data() {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Welcome', to: '/' },
          { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>

<style lang="scss">
  body, html {
    font-family: 'Helvetica Neue','Segoe UI',Helvetica,Arial,sans-serif;
    color: #4c4c4c;
    font-size: 16px;
  }
  h1, h2, h3, h4, h5, h6 {
    font-family: futura-pt,'Futura PT',Futura,'Helvetica Neue','Segoe UI',Helvetica,Arial,sans-serif;
    margin-block-start: 0.83em;
    margin-block-end: 0.83em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
  }
  header {
    text-align: center;
    h1, h3 {
      margin: 0;
    }
  }
  section {
    margin-bottom: 64px;
  }
</style>