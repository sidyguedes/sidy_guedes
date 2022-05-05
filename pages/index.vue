<template>
  <div align="center" class="main">
    <v-container class="mt-10">
      <v-avatar color="grey lighten-2" size="128">
        <v-img class="profile-picture px-2" src="1.jpg" alt="SG"></v-img>
      </v-avatar>
      <div class="mt-3 d-flex flex-column">
        <span class="title-name">Sidy Guedes</span>
        <span class="title-role">Web developer</span>
      </div>
      <div class="social-media text-center pa-5">
        <a class="px-1" href="#" target="_blank">
          <v-icon class="media-icon" color="#323232">mdi-instagram</v-icon>
        </a>
        <a class="px-1" href="#" target="_blank">
          <v-icon class="media-icon" color="#323232">mdi-linkedin</v-icon>
        </a>
        <a class="px-1" href="#" target="_blank">
          <v-icon class="media-icon" color="#323232">mdi-github</v-icon>
        </a>
      </div>
        <div color="transparent" class="d-flex flex-row justify-center" flat tile>
          <span class="pa-4">
            2
            <p class="title-role">Years of <br>Work</p>
          </span>
          <span class="pa-4">
            4
          <p class="title-role">Completed <br>Projects</p>
          </span>
          <span class="pa-4">
            4
            <p class="title-role">Satisfied <br>Costumers</p>
          </span>
        </div>
      <div class="resume-download">
        <v-row>
          <v-col cols="6">
            <div align="right">
              <v-btn depressed height="55" large dark color="#36aae4"
                class="font-weight-bold text-capitalize btn-download">
                Resume
                <v-icon right dark>
                  mdi-cloud-download-outline
                </v-icon>
              </v-btn>
            </div>
          </v-col>
          <v-col cols="6">
            <div align="left">
              <v-chip label class="mt-3">
                <a class="px-1" href="#" target="_blank">
                  <v-icon color="#323232">mdi-whatsapp</v-icon>
                </a>
              </v-chip>
              <v-chip label class="mt-3">
                <a class="px-1" href="#" target="_blank">
                  <v-icon color="#323232">mdi-facebook-messenger</v-icon>
                </a>
              </v-chip>
            </div>
          </v-col>
        </v-row>
        <v-row justify="center">
          <div class="div-filter">
            <v-btn-toggle width="auto" background-color="#fffff" v-model="toggle_exclusive">
              <v-btn class="font-weight-bold" color="white" @click="showContentFilter('prj')">Projects</v-btn>
              <v-btn class="font-weight-bold" color="white" @click="showContentFilter('skl')">Skills</v-btn>
            </v-btn-toggle>
          </div>
        </v-row>
      </div>
      <div class="mt-0 content-show">
        <Transition name="bounce">
          <div v-if="showProjects" class="col-8 ">
            <v-row>
              <v-col v-for="n in 4" :key="n" class="d-flex child-flex" cols="12" md="6" lg="6">
                <v-card :key="n" class="mx-auto card-project" max-width="344">
                  <v-img src="https://picsum.photos/500/300?image=6" height="200px"></v-img>
                  <v-card-title>
                    Nome Projeto
                  </v-card-title>
                  <v-card-subtitle class="text-left">
                    Javascript, HTML, CSS, VueJS
                  </v-card-subtitle>
                  <v-card-actions>
                    <v-btn small dark outlined color="#36aae4">
                      Ver no github
                    </v-btn>
                    <v-spacer></v-spacer>
                  </v-card-actions>
                </v-card>
              </v-col>
              </v-row>
          </div>
        </Transition>
        <Transition name="bounce">
          <div align="stretch" v-if="showSkills" class="col-6 d-flex justify-start align-start">
            <div class="box-front col-6" style="border-right: 1px solid grey;">
               <span class="text-center font-weight-bold">Frontend developer</span>
              <v-row class="ma-3 text-left">
                <v-col class="caption font-weight-bold grey--text"> <v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> Bootstrap</v-col>
                <v-col class="caption font-weight-bold grey--text"> <v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> Javascript</v-col>
              </v-row>
              <v-row class="ma-3 text-left">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> HTML</v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> VueJS</v-col>
              </v-row>
              <v-row class="ma-3 text-left">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> CSS</v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> Git</v-col>
              </v-row>
            </div>
            <div class="box-back col-6">
              <span class="text-center font-weight-bold">Backend developer</span>
              <v-row class="ma-1 text-left">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> PHP</v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon> MySQL</v-col>
              </v-row>
            </div>
          </div>
        </Transition>
      </div>
    </v-container>
    <v-footer padless class="foooter">
      <v-card class="flex" flat tile>
        <v-card-text class="py-2 grey--text text-center">
          {{ new Date().getFullYear() }} — <strong>Sidgley Guedes</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        showProjects: true,
        showSkills: false,
        toggle_exclusive: undefined,
      }
    },

    methods: {
      showContentFilter(value) {
        if (value == 'prj') {
          this.showSkills = false;
          this.showProjects = true;
        } else if (value == 'skl') {
          this.showSkills = true;
          this.showProjects = false;
        }
      }
    }
  }

</script>
<style lang="scss">
  .v-application--wrap {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    background: radial-gradient(circle, rgba(255, 255, 255, 1) 63%, rgba(221, 221, 221, 1) 100%);
  }
  .main {
    .title-role {
      font-size: 14px;
      color: #8d8c8c;
    }
    .title-name {
      font-size: 18px;
    }
    color: #494949;

    a {
      text-decoration: none;
    }

    .media-icon:hover {
      color: #36aae4 !important;
    }

    .profile-picture {
      border: 4px solid #36aae4;
    }

    .div-filter {
      margin: 2rem 0 2.5rem;
      background-color: #d0d0d0;
      padding: .375rem;
      border-radius: .75rem;
      display: flex;
      justify-content: space-between;
      column-gap: .5rem;

    }

    .btn-download {
      border-radius: 8px;
    }

    //-------BEGINING OF CSS TRANSICTION-----------
   .bounce-enter-active {
      animation: bounce-in 0.5s;
    }
    .bounce-leave-active {
      animation: bounce-in 0.5s reverse;
    }
    @keyframes bounce-in {
      0% {
        transform: scale(0);
      }
      50% {
        transform: scale(1.25);
      }
      100% {
        transform: scale(1);
      }
    }
    //--------------END OF CSS TRANSITION---------------
    .card-project{
      border-radius: 15px;
      transition: all .2s ease-in-out;
    }
    .card-project:hover { transform: scale(1.1); }

    .v-footer {
      background-color: transparent;
      .v-card {
        background-color: transparent;
      }
    }
  }

</style>
