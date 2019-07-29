<template>
  <v-container id="container-full">
    <v-layout text-xs-center wrap mt-5 px-3 py-3 id="home">
      <v-flex xs12>
        <span class="display-2 font-weight-bold">INTRODUCE</span>
      </v-flex>
    </v-layout>

    <!-- My Profile -->
    <!-- Twitter, Facebook, Wantedly, Github, Qiita, connpass icon-->
    <v-card class="mx-auto" max-width="550" tile>
      <v-list-item two-line>
        <v-list-item-content>
          <v-list-item-title class="display-2 font-weight-bold">Ussy</v-list-item-title>
          <v-list-item-group v-model="job">
            <v-list-item v-for="(job, i) in jobs" :key="i">
              <v-list-item-icon>
                <v-icon v-text="job.icon"></v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title v-text="job.text"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list-item-content>

        <v-list-item-avatar tile size="250">
          <v-img class="white--text" height="200px" v-bind:src="require('@/assets/ussy.jpg')"></v-img>
        </v-list-item-avatar>
      </v-list-item>
    </v-card>

    <!-- Skill -->
    <v-layout text-xs-center mt-10 px-3 py-3>
      <v-flex xs12>
        <span class="display-2 font-weight-bold white--text" id="skills">Skills</span>
      </v-flex>
      <v-flex xs12 mt-10>
        <headline title="Skills" />
        <cloud
          :data="skills"
          :font-size-mapper="fontSizeMapper"
          :on-word-click="onWordClick"
          :font="font"
        />
      </v-flex>
    </v-layout>

    <!-- Career -->
    <v-layout text-xs-center mt-10 px-3 py-3>
      <v-flex xs12>
        <span class="display-2 font-weight-bold" id="career">Career</span>
      </v-flex>
    </v-layout>
    <v-layout px-5 py-5>
      <v-flex xs12>
        <v-timeline>
          <!-- non career equaled to student -->
          <v-timeline-item color="green" fill-dot left>
            <v-card>
              <v-card-title class="green">
                <h2 class="display-1 white--text font-weight-light">Tokyo University of Science</h2>
              </v-card-title>
              <v-container>
                <v-layout>
                  <v-flex xs10>Majored in Machine Learning (Classifier)</v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </v-timeline-item>

          <!-- 1st career -->
          <v-timeline-item color="blue" fill-dot right>
            <v-card>
              <v-card-title class="blue">
                <h2 class="display-1 white--text font-weight-light">KDDI</h2>
              </v-card-title>
              <v-container>
                <v-layout>
                  <v-flex xs10>Android App Engineer</v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </v-timeline-item>

          <!-- 2nd career -->
          <v-timeline-item color="red" fill-dot left small>
            <v-card>
              <v-card-title class="red justify-end">
                <h2 class="display-1 mr-3 white--text font-weight-light">Yahoo! JAPAN</h2>
              </v-card-title>
              <v-container>
                <v-layout>
                  <v-flex xs10>Android App Engineer, Scrum Master, QA Engineer</v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </v-timeline-item>

          <!-- 3rd career -->
          <v-timeline-item color="cyan lighten-1" fill-dot right large>
            <v-card>
              <v-card-title class="cyan lighten-1">
                <h2 class="display-1 white--text font-weight-light">Supporterz</h2>
              </v-card-title>
              <v-container>
                <v-layout>
                  <v-flex
                    xs10
                  >Career advisor for engineers, Supporterz colab organizer, Engineer, Web marketer</v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </v-timeline-item>
        </v-timeline>
      </v-flex>
    </v-layout>
    <!-- 4th activity -->
    <v-layout text-xs-center wrap mt-5 px-3 py-3 id="activity">
      <v-flex xs12>
        <span class="display-2 font-weight-bold">ACTIVITY</span>
      </v-flex>
    </v-layout>
    <!-- WIP spekerdeck-->
  </v-container>
</template>

<script>
import Cloud from "vue-d3-cloud";

export default {
  components: {
    Cloud
  },
  data: () => ({
    jobs: [
      {
        text: "キャリアアドバイザー",
        icon: "mdi-account"
      },
      {
        text: "勉強会オーガナイザー",
        icon: "mdi-account"
      },
      {
        text: "エンジニア",
        icon: "mdi-account"
      },
      {
        text: "WEBマーケター",
        icon: "mdi-account"
      }
    ],
    skills: [
      { text: "Vue.js", value: 20 },
      { text: "HTML5", value: 40 },
      { text: "CSS", value: 30 },
      { text: "Laravel", value: 30 },
      { text: "Java", value: 70 },
      { text: "Kotlin", value: 100 },
      { text: "Python", value: 100 },
      { text: "Django", value: 50 },
      { text: "Machine Learning", value: 70 },
      { text: "Ruby", value: 70 },
      { text: "RubyonRails", value: 30 },
      { text: "Shell", value: 40 },
      { text: "Selenium", value: 30 },
      { text: "Test Case Design", value: 80 },
      { text: "SQL", value: 70 },
      { text: "Docker", value: 40 },
      { text: "Jenkins", value: 60 },
      { text: "AWS", value: 30 },
      { text: "AWS Lambda", value: 40 },
      { text: "Google Analytics", value: 30 },
      { text: "Google Apps Script", value: 40 },
      { text: "git/Github", value: 80 },
      { text: "JIRA", value: 80 },
      { text: "Confluence", value: 80 },
      { text: "Redmine", value: 60 },
      { text: "Slack", value: 100 }
    ],
    fontSizeMapper: word => Math.log2(word.value) * 9,
    onWordClick: () => {},
    font: "Impact"
  })
};
</script>

<style>
#container-full {
  padding: 0;
  max-width: 1000px;
}
.v-carousel {
  box-shadow: 0 0 0 0;
}
.wordCloud >>> svg {
  width: 100%;
}
</style>
