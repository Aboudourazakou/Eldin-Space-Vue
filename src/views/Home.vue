<template>
  <v-layout column justify-center align-center class="mt-4 pt-2">
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
    />
    <VueCompareImage
      class="hidden-lg-and-up"
      hover
      :style="{ maxWidth: '400px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage2"
      :rightImage="rightImage2"
      :sliderPositionPercentage="sliderPosition"
    />

    <br />

    <vue-typer class="headline" :repeat="0" text="TETEREOU Aboudourazakou"></vue-typer>
    <vue-typer
      :text="text1"
      :repeat="Infinity"
      :shuffle="false"
      initial-action="erasing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="1980"
      :erase-delay="150"
      erase-style="select-back"
      :erase-on-complete="false"
      caret-animation="smooth"
    ></vue-typer>
    <br />
    <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">
              <span>About</span>
              <span class="green--text">Me</span>
            </h3>
            <div>
              <p>
                Hello ,I'm TETEREOU Aboudourazakou,I'm computer sciences engineer student.I'm full -stack Developer.I'm passionate about
                <span
                  class="green--text font-weight-bold"
                >JAVA</span>,
                <span class="green--text font-weight-bold">PHP</span>,
                <span class="green--text font-weight-bold">Javascript</span> and
                <span class="green--text font-weight-bold">C++</span> as programming languages.
                Regarding frameworks, I am particularly interested
                <span
                  class="red--text font-weight-bold"
                >Spring MVC</span>,
                <span class="red--text font-weight-bold">LARAVEL PHP</span>,
                <span class="red--text font-weight-bold">VUEJS(Vuetify,NuxtJs,BootstrapVue)</span>,
                <span class="red--text font-weight-bold">Flutter</span> and
                <span class="red--text font-weight-bold">Bootstrap Css</span>. With each framework I have already done my personal projects where some source codes are available on github.
                With these technologies, I managed to carry out about fifteen freelance projects or just for fun. To know more about these projects, there is a special link regarding my projects.Although coding is my hobby, I am also interested in Sport, strolling, movies.I also like to talking with my friends about technologies in order to be up to date with new technologies.
              </p>
            </div>
          </div>
        </v-card-title>

        <v-card-actions class="hidden-sm-and-down">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-card-actions class="hidden-md-and-up justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            small
            fab
            dark
            outline
            color="green"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import { VueTyper } from "vue-typer";
import VueCompareImage from "vue-compare-image";
import axios from "axios";

export default {
  metaInfo: {
    title: "Home",
    titleTemplate: "%s ← Eldin's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      { name: "description", content: "TETEREOU Aboudourazakou's Portfolio" },
      { charset: "utf-8" },
      { property: "og:title", content: "TETEREOU Aboudourazakou" },
      { property: "og:site_name", content: "TETEREOU Aboudourazakou" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://tetereou-aboudourazakou.com" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content: "TETEREOU Aboudourazakou's Portfolio"
      }
    ]
  },
  components: {
    "vue-typer": VueTyper,
    VueCompareImage
  },
  data() {
    return {
      user: {
        nom: "Tetereou"
      },
      icons: [
        { href: "https://github.com/Aboudourazakou", icon: "fab fa-github" },
        {
          href:
            "https://stackoverflow.com/users/13389594/tetereou-mouhammad-abdourazak",
          icon: "fab fa-stack-overflow"
        },
        { href: "https://twitter.com/AboudourazakouT", icon: "fab fa-twitter" },
        {
          href:
            "https://www.linkedin.com/in/aboudourazakou-tetereou-2189b2159/",
          icon: "fab fa-linkedin-in"
        },

        {
          href: "https://www.facebook.com/tetereou.abdourazak",
          icon: "fab fa-facebook-f"
        },
        {
          href: "https://www.instagram.com/ing_abdourazak/",
          icon: "fab fa-instagram"
        }
      ],
      text1: [
        "Full stack developper",
        "Desktop developper",
        "Mobile developper",
        "Engineer student"
      ],
      leftImage: "https://i.imgur.com/bU50uS9.jpg",
      rightImage: "essai.png",
      leftImage2: "tetereou-blanche.png",
      rightImage2: "tetereou-original.png",
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5
    };
  },


};
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}

.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: green;
}
.vue-typer .custom.char.selected {
  color: #e91e63;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: green;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}
</style>

