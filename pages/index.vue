<template>
  <div>
    <div
      class="navigation-container">
      <nav class="navigation">
        <ul>
          <li class="active" data-nav="section-1"><a href="#section-1"><span>section 1</span></a></li>
          <li data-nav="section-2"><a href="#section-2"><span>section 2</span></a></li>
          <li data-nav="section-3"><a href="#section-3"><span>section 3</span></a></li>
          <li data-nav="section-4"><a href="#section-4"><span>section 4</span></a></li>
          <li data-nav="section-5"><a href="#section-5"><span>section 5</span></a></li>
        </ul>
      </nav>
    </div>
    <v-container
      fluid>
      <v-layout
        row
        wrap>
        <v-flex md2/>
        <v-flex md2>
          <header>
            <h3>Ventures of the</h3>
            <h1>Penumbra</h1>
            <h1>Mafia</h1>
            <hr>
          </header>
          <section id="section-1" class="story active">
            <h2>Meet the Dons who run Silicon Valley – the PayPal Mafia.</h2>
            <p>Despite the name, this ‘outfit’ is an entirely legit group of tech entrepreneurs - the founders and former employees of PayPal. The ‘Mafia’ have continued to work and invest together since the company’s 2002 sale to eBay. Between them, they’ve founded, funded or led some of the world’s biggest tech firms</p>
          </section>
          <section id="section-2" class="story">
            <h2>Household names</h2>
            <p>Besides PayPal, the Mafia are connected to many other notable brands. Steve Chen, Chad Hurley and Jawed Karim worked at PayPal before they founded YouTube in 2005. Yelp and LinkedIn were also started by PayPal Mafiosi.</p>
          </section>
          <section id="section-3" class="story">
            <h2>Fingers in every pie</h2>
            <p>Although most of the PayPal Mafia’s investments have stayed within their traditional territory of Silicon Valley tech, more unusual Family ventures have included private spaceflight company SpaceX, Hollywood movie Thank You for Smoking and political campaign group FWD.us.</p>
          </section>
          <section id="section-4" class="story">
            <h2>Follow the money</h2>
            <p>In addition to exec roles and individual investments in over 400 companies, several of these Bosses have started and contributed to some of Silicon Valley’s biggest investment funds, giving them a piece of the action in thousands more.</p>
          </section>
          <section id="section-5" class="story">
            <h2>Capisce? Now investigate the connections for yourself</h2>
            <p>Explore the visualisation to see the many companies the PayPal Mafia are involved in, and find out which well-known brands they helped shape. See how the Mafiosi remain connected through numerous joint ventures in Silicon Valley and beyond.</p>
          </section>
          <footer>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vero voluptatibus sit incidunt impedit natus quibusdam ea aut quam magnam, fugit. Ipsam, vitae, cupiditate. At alias hic, sapiente, eveniet recusandae labore!
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Neque consequatur, repudiandae dicta animi ab blanditiis esse, laudantium necessitatibus quisquam inventore quae fugiat. Similique voluptates a quos sint impedit, dolore, aliquam.
          </footer>
        </v-flex>
        <v-flex
          md8>
          visualization
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
  import JQuery from 'jquery';
  import smoothScroll from '~/plugins/smooth-scroll';
  const $ = JQuery;

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
    },

    mounted() {
      // $('.sections').slick({
      //   dots: true,
      //   arrows: false,
      //   vertical: true,
      //   slidesToShow: 4,
      //   dotsClass: 'nav-dots'
      // });
      $('.navigation a').smoothScroll({
        offset: -240,
        afterScroll: function(options) {
          const $el = $(options.link).parent();
          const $tgt = $(options.scrollTarget);
          $el.addClass('active');
          $el.siblings().removeClass('active');
          $tgt.addClass('active');
          $tgt.siblings('section').removeClass('active');
        }
      });

      // $(window).scroll(function(){
      //   var scrollTop = $(window).scrollTop();
      //   var windowHeight = $(window).height();
      //   var first = false;
      //   $("section.story").each( function() {
      //     var offset = $(this).offset();
      //     if (scrollTop <= offset.top && ($(this).height() + offset.top) < (scrollTop + windowHeight) && first == false) {
      //       var section = $(this).attr('id');
      //       var $section = $('#' + section);
      //       var $nav = $('.navigation li[data-nav="' + section + '"]');
      //       console.log('.navigation li[data-nav="' + section + '"]');
      //       $nav.addClass('active');
      //       $nav.siblings().removeClass('active');
      //       $section.addClass('active');
      //       $section.siblings('section').removeClass('active');
      //       first=true;
      //     } else {
      //       // $(this).removeClass("first");
      //       first=false;
      //     }
      //   });
      // });
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
    max-width: 320px;
    color: #4c4c4c;
    opacity: 0.2;
    transition: 0.12s ease opacity;
  }

  section.active {
    opacity: 1;
  }

  .navigation-container {
    position: fixed;
    right: 0;
    top: 50%;
    margin-top: -60px;
  }
  .navigation {
    // background-color: gray;
    width: 60px;

    ul {list-style: none;}
    li {margin-bottom: 12px;}
    li a span {display:none;}
    li a::before {
      display: inline-block;
      content: '';
      -webkit-border-radius: 0.375rem;
      border-radius: 0.375rem;
      height: 0.75rem;
      width: 0.75rem;
      margin-right: 0.5rem;
      border: 2px solid #bdbdbd;
    }
    li.active a::before {
      background-color: #4c4c4c;
      border: 2px solid #4c4c4c;
    }

  }
</style>