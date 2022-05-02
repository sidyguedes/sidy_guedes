<template>
  <div align="center" class="main">
    <v-container class="mt-10">
      <v-avatar color="grey lighten-2" size="128">
        <v-img class="profile-picture px-2" src="1.jpg" alt="SG"></v-img>
      </v-avatar>
      <div class="mt-3 d-flex flex-column">
        <span class="title font-weight-bold">Sidy Guedes</span>
        <span class="caption font-weight-bold">Web developer</span>
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
      <div>
        <v-card color="transparent" class="d-flex flex-row justify-center" flat tile>
          <span class="pa-4 font-weight-bold">
            3
            <p class="grey--text caption font-weight-bold">Years of <br>Work</p>
          </span>
          <span class="pa-4 font-weight-bold">
            +50
            <p class="grey--text caption font-weight-bold">Completed <br>Projects</p>
          </span>
          <span class="pa-4 font-weight-bold">
            96
            <p class="grey--text caption font-weight-bold">Satisfied <br>Costumers</p>
          </span>
        </v-card>
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
            <v-btn-toggle background-color="#d0d0d0" v-model="toggle_exclusive">
              <v-btn class="font-weight-bold" color="white" @click="showContentFilter('prj')">Projects</v-btn>
              <v-btn class="font-weight-bold" color="white" @click="showContentFilter('skl')">Skills</v-btn>
            </v-btn-toggle>
          </div>
        </v-row>
      </div>
      <div class="mt-0 content-show">
        <Transition name="slide-fade">
          <div v-if="showSkills" class="col-8 d-flex flex-row">
            <div class="box-front col-6">
               <span class="text-center font-weight-bold">Frontend developer</span>
              <v-row class="ma-3">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>HTML</span></v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>VueJS</span></v-col>
              </v-row>
              <v-row class="ma-3">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>CSS</span></v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>Bootstrap</span></v-col>
              </v-row>
              <v-row class="ma-3">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>Javascript</span></v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>Git</span></v-col>
              </v-row>
            </div>
            <div class="box-back col-6" >
              <span class="text-center font-weight-bold">Backend developer</span>
              <v-row class="ma-3">
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>PHP</span></v-col>
                <v-col class="caption font-weight-bold grey--text"><v-icon small color="#36aae4">mdi-checkbox-marked-circle-outline</v-icon><span>MySQL</span></v-col>
              </v-row>
            </div>
          </div>
        </Transition>
        <Transition name="slide-fade">
          <div v-if="showProjects" class="text-center col-8">
            <v-row align-content="center">
              <v-col v-for="n in 4" :key="n" class="d-flex child-flex" cols="12" md="6" lg="6">
                <v-img :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                  :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`" aspect-ratio="1" class="grey lighten-2">
                  <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
              </v-col>
            </v-row>
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
    //background-image: linear-gradient(to bottom, #ffffff, #f8f8f8, #f0f0f0, #e9e9e9, #e2e2e2);
    background: radial-gradient(circle, rgba(255, 255, 255, 1) 63%, rgba(221, 221, 221, 1) 100%);

  }

  .main {
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
    // .slide-fade-enter-active {
    //   transition: all 0.2s ease-out;
    // }

    // .slide-fade-leave-active {
    //   transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
    // }

    // .slide-fade-enter-from,
    // .slide-fade-leave-to {
    //   transform: translateX(20px);
    //   opacity: 0;
    // }
    //--------------END OF CSS TRANSITION---------------

    .footer {
      background: radial-gradient(circle, rgba(255, 255, 255, 1) 63%, rgba(221, 221, 221, 1) 100%) !important;
    }
  }

</style>
