<template>
  <div align="center" class="main container">
    <v-container class="mt-10">
      <v-avatar color="grey lighten-2" size="128">
        <v-img class="profile-picture px-2" src="1.jpg" alt="SG"></v-img>
      </v-avatar>
      <div class="mt-3 name">
        <span class="title pt-5 font-weight-bold">Sidy Guedes</span>
      </div>
      <div class="">
        <span class="caption pt-5 font-weight-bold">Web developer</span>
      </div>
      <div class="social-media text-center pa-5">
        <a class="px-1" href="#" target="_blank">
          <v-icon color="#323232">mdi-instagram</v-icon>
        </a>
        <a class="px-1" href="#" target="_blank">
          <v-icon color="#323232">mdi-linkedin</v-icon>
        </a>
        <a class="px-1" href="#" target="_blank">
          <v-icon color="#323232">mdi-github</v-icon>
        </a>
      </div>
      <div>
        <v-card class="d-flex flex-row justify-center" flat tile>
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
              <v-btn depressed dark color="#36aae4" class="font-weight-bold text-capitalize btn-download">
                Resume
                <v-icon right dark>
                  mdi-cloud-download-outline
                </v-icon>
              </v-btn>
            </div>
          </v-col>
            <v-col cols="6">
              <div align="left" class="">
                <v-chip label>
                  <a class="px-1" href="#" target="_blank">
                    <v-icon color="#323232">mdi-whatsapp</v-icon>
                  </a>
                </v-chip>
                <v-chip label>
                  <a class="px-1" href="#" target="_blank">
                    <v-icon color="#323232">mdi-facebook-messenger</v-icon>
                  </a>
                </v-chip>
              </div>
          </v-col>
        </v-row>
      </div>
    </v-container>
  </div>
</template>

<script>
  export default {

  }

</script>
<style lang="scss">
  .main {
    color: #494949;

    a {
      text-decoration: none;
    }

    .profile-picture {
      border: 4px solid #36aae4;
    }
  }

</style>
