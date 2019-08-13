<template>
  <v-container id="container-full">
    <v-layout text-xs-center wrap mt-5 px-3 py-3>
      <v-flex xs12>
        <span class="display-2 font-weight-bold" id="home">Introduce</span>
      </v-flex>
    </v-layout>

    <!-- My Profile -->
    <section>
      <v-layout column wrap class="my-8" align-center>
        <v-container grid-list-xl>
          <v-layout row wrap align-content-start>
            <v-flex xs12 md4 align-center>
              <v-card :loading="loading" class="transparent mx-auto my-12" flat max-width="374">
                <v-layout justify-center>
                  <v-avatar size="150">
                    <img v-bind:src="require('@/assets/ussy.jpg')" alt="avatar" />
                  </v-avatar>
                </v-layout>

                <v-card-title class="white--text">Ussy (うっしー)</v-card-title>
                <v-card-text>
                  <div
                    class="gray--text"
                    style="font-weight:bold"
                  >エンジニア(Django, GAS)/ Web marketer(Twitter, Facebook, Google Analytics) / 勉強会主催・運営(connpass, SupporterzCoLab)</div>
                  <a href="https://supporterz.jp/">
                    <div class="my-4 subtitle-1 blue--text">Supporterz Inc.</div>
                  </a>
                  <div class="white--text">若手エンジニア向けの転職支援</div>
                  <a href="https://supporterzcolab.com/dashboard/">
                    <div class="my-4 subtitle-1 blue--text">Supporterz CoLab</div>
                  </a>
                  <div class="white--text">若手エンジニアのための勉強会 connpassの姉妹サイト</div>
                </v-card-text>

                <v-divider class="mx-4"></v-divider>

                <v-card-text>
                  <div class="subheading">Accounts</div>
                  <v-btn v-for="website in websites" :key="website" class="mx-2 my-2" fab icon>
                    <a v-bind:href="website.link">
                      <v-avatar size="45">
                        <img v-bind:src="website.icon" alt="avatar" />
                      </v-avatar>
                    </a>
                  </v-btn>
                </v-card-text>
              </v-card>
            </v-flex>

            <v-flex md8 align-center>
              <v-card :loading="loading" class="transparent mx-auto my-12" flat>
                <v-card-title class="display-2 green--text">Biography</v-card-title>
                <v-card-text class="font-weight-bold white--text my-6 mx-4">
                  <div class="biotext" style="white-space:pre-line">{{ bioBody }}</div>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-layout>
    </section>

    <!-- Skill -->
    <section>
      <v-layout text-xs-center mt-10 px-3 py-3>
        <v-flex xs12>
          <a class="display-2 font-weight-bold white--text anchor" id="skills">Skill</a>
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
    </section>

    <!-- Career -->
    <section>
      <v-layout text-xs-center mt-10 px-3 py-3>
        <v-flex xs12>
          <a class="display-2 font-weight-bold white--text anchor" id="career">Career</a>
        </v-flex>
      </v-layout>
      <v-layout px-5 py-5>
        <v-flex xs12>
          <v-timeline>
            <!-- non career equaled to student -->
            <v-timeline-item color="green" fill-dot left>
              <v-card>
                <v-card-title class="green">
                  <h2 class="display-1 white--text font-weight-bold">Tokyo University of Science</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex xs10 class="font-weight-bold my-2">機械学習・データマイニングを大学院で専攻</v-flex>
                    <v-flex xs10>ヒトや動物の生体データ(血液のデータ、活動データ etc...)を用いて疾病の予測を主に行い、国際学会に3回ほど参加</v-flex>
                    <v-flex xs10>
                      <a
                        href="https://news.mynavi.jp/article/20160808-a312/"
                      >うち1プロジェクトは農林水産省の「革新的技術開発・緊急展開事業」に採択</a>
                    </v-flex>
                    <v-flex xs10 class="font-weight-bold my-2">言語・ツール類</v-flex>
                    <v-flex xs8>
                      <ul>
                        <li>Python3.4, MySQL</li>
                        <li>Numpy, Scipy, Pandas, requests, Selenium</li>
                        <li>Scikit-learn, xgboost</li>
                      </ul>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-timeline-item>

            <!-- 1st career -->
            <v-timeline-item color="blue" fill-dot right>
              <v-card>
                <v-card-title class="blue">
                  <h2 class="display-1 white--text font-weight-bold">KDDI</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex xs10 class="font-weight-bold my-2">Android App Engineer</v-flex>
                    <v-flex xs10>
                      <a href="https://www.au.com/mobile/service/au-service-top/">ニュース系アプリ</a>の開発に従事
                    </v-flex>
                    <v-flex xs10>ニュースの新規タブ、新規広告、Kotlinへのリファクタリング、CI/CDの整備、自社CDNサイト(Laravel)の機能改修を担当</v-flex>
                    <v-flex xs10 class="font-weight-bold my-2">言語・ツール類</v-flex>
                    <v-flex xs8>
                      <ul>
                        <li>Java8, Kotlin1.2, Python3.6, Laravel5.5, Bash</li>
                        <li>Retrofit, Okhttp3, Gson, Picasso, Zxing</li>
                        <li>JUnit</li>
                        <li>Numpy, Scipy, Pandas, requests, Selenium</li>
                        <li>git, Github Enterprise, Charles, Jenkins, Sider, Slack</li>
                      </ul>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-timeline-item>

            <!-- 2nd career -->
            <v-timeline-item color="red" fill-dot left small>
              <v-card>
                <v-card-title class="red justify-end">
                  <h2 class="display-1 mr-3 white--text font-weight-bold">Yahoo! JAPAN</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex
                      xs10
                      class="font-weight-bold my-2"
                    >Android App Engineer, Scrum Master, QA Engineer</v-flex>
                    <v-flex xs10>
                      <a
                        href="https://play.google.com/store/apps/details?id=jp.co.yahoo.android.ybrowser&hl=ja"
                      >ブラウザアプリ</a>の開発に従事
                    </v-flex>
                    <v-flex xs10>
                      レビューに基づいた機能改修とA/Bテスト施策、
                      <a
                        href="https://www.itmedia.co.jp/news/articles/1907/03/news107.html"
                        class="font-weight-bold"
                      >AIを活用した類似画像検索</a>、Kotlinへのリファクタリング、チケット管理やQA環境の整備、オフショアのエンジニアとの連携
                    </v-flex>
                    <v-flex xs10 class="font-weight-bold my-2">言語・ツール類</v-flex>
                    <v-flex xs8>
                      <ul>
                        <li>Java8, Kotlin1.3, Bash</li>
                        <li>Gson, AAC, AndroidX, Rx, Zxing</li>
                        <li>Espresso, JUnit4, Robolectric</li>
                        <li>git, Github Enterprise, JIRA, Confluence, Zeplin</li>
                        <li>SmartBeat, Screwdriver.cd, Zoom, Bluejeans, Slack</li>
                      </ul>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-timeline-item>

            <!-- 3rd career -->
            <v-timeline-item color="cyan lighten-1" fill-dot right large>
              <v-card>
                <v-card-title class="cyan lighten-1">
                  <h2 class="display-1 white--text font-weight-bold">サポーターズ</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex
                      xs10
                      class="font-weight-bold my-2"
                    >若手エンジニア向けキャリアアドバイザー、勉強会企画・運営・主催者、ウェブマーケター</v-flex>
                    <v-flex xs10>エンジニアの経験をもとに、若手エンジニア向けのキャリア相談と転職支援に寄り添う</v-flex>
                    <v-flex xs10>
                      また、若手エンジニアのアウトプット・インプットの機会を提供する
                      <a href="https://supporterzcolab.com/">自社勉強会</a>の主催者・企画・運営を一括で担当
                    </v-flex>
                    <v-flex xs10>加えてビジネスサイド側との連携のために自社サイトの一部改修やGoogleAppsScriptを使用した自動化等を担当</v-flex>
                    <v-flex xs10 class="font-weight-bold my-2">言語・ツール類</v-flex>
                    <v-flex xs8>
                      <ul>
                        <li>Django, Google Apps Script</li>
                        <li>git, Github, Google Analytics, Twitter, Facebook</li>
                        <li>HRMOS, SARDINE, Slack, Gsuite</li>
                      </ul>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </v-flex>
      </v-layout>
    </section>

    <!-- 4th activity -->
    <v-layout text-xs-center wrap mt-5 px-3 py-3>
      <v-flex xs12>
        <a class="display-2 font-weight-bold white--text anchor" id="activity">Activity</a>
      </v-flex>
    </v-layout>
    <section>
      <v-card class="mx-auto my-8" max-width="860">
        <v-container fluid grid-list-md pa-2>
          <v-layout wrap>
            <v-flex v-for="card in cards" :key="card.title" v-bind="{ [`xs${card.flex}`]: true }">
              <v-card color="gray">
                <a v-bind:href="card.link">
                  <v-img :src="card.src" class="white--text" height="300px" />
                </a>

                <v-card-title class="fill-height align-end green--text" v-text="card.title"></v-card-title>
                <v-spacer />
                <v-card-text class="white--text font-weight-bold">{{card.description}}</v-card-text>
                <v-card-actions>
                  <v-layout v-if="card.source != ''" justify-end>
                    <a v-bind:href="card.source">
                      <img
                        src="https://visualpharm.com/assets/171/Play%20Property-595b40b65ba036ed117d158a.svg"
                        height="50px"
                      />
                    </a>
                  </v-layout>
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
    </section>
  </v-container>
</template>

<script>
import Cloud from "vue-d3-cloud";

export default {
  components: {
    Cloud
  },
  data: () => ({
    bioBody: `大学院にて機械学習を専攻後、新卒でAndroidアプリエンジニアに。ニュースアプリの新規タブ追加、広告追加、Kotlinへのリファクタリング、Jenkinsを用いたCI/CD整備、スクラム開発の推進を担当。
    その後転職し、引き続きAndroidアプリエンジニアとしてブラウザーアプリの開発担当、QAやスクラムマスターも付随的に行う。\n
    元々人や組織の事を考えるのが好きだったことと、転職する過程で様々な人からキャリアの相談を受ける中で、エンジニアがキャリアに悩んでいることに気づき、キャリアアドバイザーとして現職に。\n
    キャリアアドバイザーとして転職・キャリア相談に乗るだけではなく、エンジニアがキャリアアップを図るため・キャリアを見つける手がかりにするために勉強会を企画・開催・運営している。`,
    websites: [
      {
        text: "Twitter",
        link: "https://twitter.com/shoushi12",
        icon: require("@/assets/twitter-logo.png")
      },
      {
        text: "Facebook",
        link: "https://www.facebook.com/people/Sho-Ushikubo/100014055931970",
        icon: require("@/assets/facebook-logo.png")
      },
      {
        text: "Github",
        link: "https://github.com/sudo5in5k",
        icon: require("@/assets/github-logo.jpg")
      },
      {
        text: "Qiita",
        link: "https://qiita.com/sudo5in5k",
        icon: require("@/assets/qiita-logo.png")
      },
      {
        text: "Wantedly",
        link: "https://www.wantedly.com/users/78524630",
        icon: require("@/assets/wantedly-logo.png")
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
    cards: [
      {
        title: "サポーターズCoLab",
        src: "https://corp.supporterz.jp/img/colab-logo.png",
        link: "https://supporterzcolab.com/",
        description: "勉強会の企画・主催・運営を一括で担当しています",
        source: "",
        flex: 12
      },
      {
        title: "サポーターズCoLab",
        src:
          "https://img.supporterzcolab.com/thumbs/c3/38/c3389c9e0f55964d2c9ce11e282175c7.png",
        link: "https://supporterzcolab.com/event/891/",
        description:
          "キャリアアップのためのエンジニアにもわかるマーケティング・ブランディングの話をしました",
        source:
          "https://speakerdeck.com/sudo5in5k/enziniafalsetamefalsemaketeinguburandeinguru-men",
        flex: 6
      },
      {
        title: "転職LT#5",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/e0/f4/e0f4dc40bacd17cc0266bf48c510824f.png",
        link: "https://ex-sier.connpass.com/event/136868/",
        description:
          "転職LTにてエンジニア兼中途エージェントとして、転職を成功させるにはどうすればいいかお話しました",
        source: "https://speakerdeck.com/sudo5in5k/zhuan-zhi-lt-number-5",
        flex: 6
      }
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
a.anchor {
  display: block;
  padding-top: 80px;
  margin-top: -80px;
}
.v-carousel {
  box-shadow: 0 0 0 0;
}
.wordCloud >>> svg {
  width: 100%;
}
div.biotext {
  line-height: 2em;
  font-size: large;
}
</style>
