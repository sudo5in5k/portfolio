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
                <v-card-title class="white--text">Ussy</v-card-title>
                <v-card-text>
                  <div class="gray--text" style="font-weight:bold">Coming Soon...</div>
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
      </v-layout>
      <v-card class="mx-auto my-8" max-width="860" min-width="344" outlined>
        <v-container fluid grid-list-md pa-2>
          <v-layout wrap>
            <v-flex
              v-for="skill in skills"
              :key="skill.text"
              v-bind="{ [`xs${skill.flex}`]: true }"
            >
              <v-card color="gray" class="mx-auto" outlined>
                <v-list-item three-line>
                  <v-list-item-content>
                    <v-list-item-title class="green--text headline mb-1" v-text="skill.text"></v-list-item-title>
                    <v-rating
                      :value="skill.value"
                      color="amber"
                      half-increments
                      dense
                      size="14"
                      readonly
                    ></v-rating>
                    <v-list-item-subtitle class="white--text my-2">{{skill.desc}}</v-list-item-subtitle>
                  </v-list-item-content>
                  <v-list-item-avatar tile size="50">
                    <v-img :src="skill.icon"></v-img>
                  </v-list-item-avatar>
                </v-list-item>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
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
                        <li>Git, Github Enterprise, Charles, Jenkins, Sider, Slack</li>
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
                  <h2 class="display-1 white--text font-weight-bold">人材会社</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex
                      xs10
                      class="font-weight-bold my-2"
                    >若手エンジニア向けキャリアアドバイザー、勉強会企画・運営・主催者</v-flex>
                    <v-flex xs10>エンジニアの経験をもとに、若手エンジニア向けのキャリア相談と転職支援に寄り添う</v-flex>
                    <v-flex xs10>
                      また、若手エンジニアのアウトプット・インプットの機会を提供する
                      <a href="https://supporterzcolab.com/">自社勉強会</a>の主催者・企画・運営を一括で担当
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-timeline-item>

            <!-- 4th career -->
            <v-timeline-item color="pink" fill-dot left large>
              <v-card>
                <v-card-title class="pink">
                  <h2 class="display-1 white--text font-weight-bold">ベンチャー企業</h2>
                </v-card-title>
                <v-container>
                  <v-layout wrap>
                    <v-flex
                      xs10
                      class="font-weight-bold my-2"
                    >Lead Android App Engineer</v-flex>
                    <v-flex xs10>
                      やりたいことを実現するためのSNSアプリの開発に従事
                    </v-flex>
                    <v-flex xs10>
                      0->1フェーズで初めてのAndroidアプリエンジニア正社員として活動、設計のMVVM化・フルスクラッチの新規機能開発
                    </v-flex>
                    <v-flex xs10>
                      <ul>
                        <li>・会員登録の認証周り</li>
                        <li>・通知機能実装</li>
                        <li>・Twitterライクなユーザー同士のコメント投稿(画像アップロード含)と閲覧・いいね・編集・削除機能</li>
                        <li>・コレクション要素のある初回特定の実装</li>
                        <li>・抜本的な設計再編</li>
                        <li>・GithubActionsを通じたCI設計</li>
                        <li>・コーディングルールやブランチルール等運用方法策定</li>
                        <li>・ビルド環境ごとの設定作成</li>
                      </ul>
                    </v-flex>
                    <v-flex xs10 class="font-weight-bold my-2">言語・設計・ツール類</v-flex>
                    <v-flex xs8>
                      <ul>
                        <li>Kotlin1.3</li>
                        <li>MVVM(Data Binding, LiveData, corotuine)</li>
                        <li>Android Jetpack(KTX, LifeCycle, LiveData, Paging, ViewModel)</li>
                        <li>Firebase(FireStore, Crashlytics, Auth, Messaging, Analytics, Dynamic-links)</li>
                        <li>Facebook, LINE, Twitter SDK</li>
                        <li>Retrofit(Moshi-Adapter), okhttp3, GraphQL, Coroutines</li>
                        <li>マテリアルデザイン, RecyclerView, CardView</li>
                        <li>JUnit4</li>
                        <li>git, Github Enterprise, figma</li>
                        <li>Zoom, Slack</li>
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
                        src="http://icons.iconarchive.com/icons/pelfusion/long-shadow-media/256/Document-icon.png"
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
export default {
  components: {},
  data: () => ({
    bioBody: `大学時代の経験から人の意思決定を支えてあげられたら面白いと思う中で、「データの見えざる手」という本に出会い、プロダクトを通じたデータとUI/UXが意思決定を支えると確信する。\n
    その後、大学院にて機械学習を専攻後、新卒でAndroidアプリエンジニアに。大規模ニュースアプリの実装・新技術導入・スクラム推進を担当。\n
    その後転職し、引き続きAndroidアプリエンジニアとしてブラウザーアプリの開発担当・QAやスクラムマスターも付随的に行う。\n
    転職と身近な人からキャリアの相談を受ける中で身近なエンジニアがキャリアに悩んでいることに気づき、エンジニア専門のキャリアアドバイザーと勉強会のディレクターを務める。\n
    その後、人材ビジネスと自分のやりたいことのギャップを感じ、0->1ベンチャーにてAndroidエンジニアとしてリードエンジニアとして戻り活躍中。`,
    websites: [
      {
        text: "Twitter",
        link: "https://twitter.com/shoushi12",
        icon: require("@/assets/twitter-logo.png")
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
      },
      {
        text: "connpass",
        link: "https://connpass.com/user/sudo5in5k/",
        icon: require("@/assets/connpass-logo.png")
      }
    ],
    skills: [
      {
        text: "HTML5",
        value: "3.0",
        desc: "MVCフレームワーク時のView作成の業務経験あり",
        icon: "https://image.flaticon.com/icons/svg/1216/1216733.svg",
        flex: 12
      },
      {
        text: "CSS3",
        value: "3.0",
        desc: "簡単なmargin/paddingの調整、Bootstrapでの要素作成の業務経験あり",
        icon: require("@/assets/css3-logo.svg"),
        flex: 12
      },
      {
        text: "Vue.js",
        value: "3.0",
        desc: "自主学習にて簡単なレスポンシブWebページ作成経験あり",
        icon: "https://jp.vuejs.org//images/logo.png",
        flex: 12
      },
      {
        text: "Laravel",
        value: "3.0",
        desc: "ファイルアップロードのサイトの改修の業務経験あり",
        icon:
          "https://cdn4.iconfinder.com/data/icons/logos-3/256/laravel-512.png",
        flex: 12
      },
      {
        text: "Java",
        value: "4.5",
        desc:
          "オブジェクト指向・可読性の高いコード・非同期処理を扱うコードが書ける、業務経験あり",
        icon: require("@/assets/java-logo.png"),
        flex: 12
      },
      {
        text: "Kotlin",
        value: "5",
        desc:
          "オブジェクト指向・可読性の高いコード・非同期処理を扱うコードが書ける、業務経験あり",
        icon: "https://cdn.worldvectorlogo.com/logos/kotlin-1.svg",
        flex: 12
      },
      {
        text: "Python",
        value: "4.5",
        desc:
          "大学院にて機械学習・データマイニングに利用、業務経験にて自動化をする際に利用、コーディングテストにて使用",
        icon:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1024px-Python-logo-notext.svg.png",
        flex: 12
      },
      {
        text: "Django",
        value: "4",
        desc: "業務経験にてファイルアップロードサイトの自作経験あり",
        icon: "https://cdn.iconscout.com/icon/free/png-512/django-1-282754.png",
        flex: 12
      },
      {
        text: "Ruby",
        value: "3.5",
        desc: "自主学習にて簡単なコーディングが可能",
        icon: "https://cdn.worldvectorlogo.com/logos/ruby.svg",
        flex: 12
      },
      {
        text: "RubyonRails",
        value: "3.5",
        desc: "自主学習にてCRUDのポートフォリオサイトを作る際に利用",
        icon: "https://pbs.twimg.com/media/CZGHPChUAAA3jqE.png",
        flex: 12
      },
      {
        text: "Shell",
        value: "4.0",
        desc: "業務経験にてAPIアクセス、サーバー接続、CI/CDにて利用",
        icon:
          "https://cdn.pixabay.com/photo/2013/07/12/14/48/bash-148836_640.png",
        flex: 12
      },
      {
        text: "Selenium",
        value: "4.0",
        desc: "業務自動化、自動テスト(整合性確認、スナップショット)に利用",
        icon: "https://www.seleniumhq.org/images/big-logo.png",
        flex: 12
      },
      {
        text: "ソフトウェアテスト",
        value: "4.5",
        desc:
          "業務にてテスト計画からテスト設計・テスト実施まで一括でチームをリードして担当した経験あり",
        icon: "https://image.flaticon.com/icons/png/512/25/25154.png",
        flex: 12
      },
      {
        text: "SQL",
        value: "4.0",
        desc:
          "INNER JOINや要約関数が利用可能、MySQLの運用資格所持、MySQL・Redashを業務にて利用経験あり",
        icon:
          "https://icons-for-free.com/iconfiles/png/512/development+logo+mysql+icon-1320184807686758112.png",
        flex: 12
      },
      {
        text: "Docker",
        value: "3.5",
        desc: "業務にてdocker-compose.ymlやDockerfileを用いた構築経験あり",
        icon:
          "https://www.docker.com/sites/default/files/social/docker_facebook_share.png",
        flex: 12
      },
      {
        text: "Jenkins",
        value: "4.0",
        desc: "業務にてCI/CD・テスト結果・警告数結果の監視経験あり",
        icon:
          "https://wiki.jenkins.io/download/attachments/2916393/headshot.png?version=1&modificationDate=1302753947000&api=v2",
        flex: 12
      },
      {
        text: "AWS",
        value: "3.0",
        desc:
          "自主学習にてEC2インスタンス作成・Cloud Watchでの監視、Lambda・API gatewayでの簡単なAPI作成経験あり",
        icon: require("@/assets/aws-logo.png"),
        flex: 12
      },
      {
        text: "Google Analytics",
        value: "3.5",
        desc:
          "業務にてGoogle analytics構築、KPIに基づいた指標設定・運用の経験あり",
        icon:
          "https://www.gstatic.com/analytics-suite/header/suite/v2/ic_analytics.svg",
        flex: 12
      },
      {
        text: "Google Apps Script",
        value: "4",
        desc: "業務にてSpreadsheetとの連携と通知、簡単なAPI作成経験あり",
        icon:
          "https://www.gstatic.com/images/branding/product/2x/apps_script_64dp.png",
        flex: 12
      },
      {
        text: "Git",
        value: "4.5",
        desc: "業務にてGit Flow/Github Flowに基づいた運用経験あり",
        icon: "https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png",
        flex: 12
      },
      {
        text: "JIRA",
        value: "4.0",
        desc: "業務にてチケット管理経験あり",
        icon: "https://cdn.worldvectorlogo.com/logos/jira-3.svg",
        flex: 12
      },
      {
        text: "Confluence",
        value: "4.0",
        desc: "業務にてコード埋め込みを使用したドキュメント作成経験あり",
        icon:
          "https://cdn3.iconfinder.com/data/icons/social-media-2169/24/social_media_social_media_logo_confluence-512.png",
        flex: 12
      },
      {
        text: "Redmine",
        value: "4.5",
        desc: "業務にてチケット管理経験、APIを使用したサービス連携経験あり",
        icon: "http://www.redmine.org/attachments/3462/redmine_fluid_icon.png",
        flex: 12
      },
      {
        text: "Slack",
        value: "5.0",
        desc:
          "業務にてワークスペース管理経験、API/incoming outgoing webhookを使用した各種サービス連携・自動化の経験あり",
        icon:
          "https://a.slack-edge.com/4a5c4/marketing/img/meta/slack_hash_256.png",
        flex: 12
      }
    ],
    cards: [
      {
        title: "サポーターズCoLab",
        src: "https://corp.supporterz.jp/img/colab-logo.png",
        link: "https://supporterzcolab.com/",
        description:
          "若手エンジニア向け勉強会PFのマネージャーとして企画・主催・運営を担当しています",
        source: "",
        flex: 6
      },
      {
        title: "CareerKaigi",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/3e/65/3e65d001886c860feedcff1701599601.png",
        link: "https://career-kaigi.connpass.com/",
        description:
          "エンジニアのキャリアの意思決定を助けるため主催者として活動しています",
        source: "",
        flex: 6
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
          "転職LTにてエンジニア兼中途エージェントとして、転職を成功させるためのTipsを話しました",
        source: "https://speakerdeck.com/sudo5in5k/zhuan-zhi-lt-number-5",
        flex: 6
      },
      {
        title: "17卒ミートアップLT",
        src:
          "https://img.supporterzcolab.com/thumbs/89/76/897651dd1ab0c17d79a31e57f7a228b5.png",
        link: "https://supporterzcolab.com/event/901/",
        description:
          "17卒のエンジニアが集まったLT会でこれまでの自分のキャリアについて話しました",
        source: "https://speakerdeck.com/sudo5in5k/17zu-mitoatupu",
        flex: 6
      },
      {
        title: "CareerKaigi#1",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/3e/65/3e65d001886c860feedcff1701599601.png",
        link: "https://career-kaigi.connpass.com/",
        description:
          "自分の経歴と、なぜ私が今エージェントなのか、今後どうなりたいか宣言をしました",
        source:
          "https://speakerdeck.com/sudo5in5k/nazesi-haezientoninatutafalseka",
        flex: 6
      },
      {
        title: "ここだから話せるVPoEの現場",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/d6/57/d65731dde8d6302389fac0f75d7ba2ea.png",
        link: "https://kiitok.connpass.com/event/138739/",
        description:
          "kiitok主催のイベントにてブログ枠としてレポート記事を書きました",
        source: "https://ussylog.hatenablog.com/entry/2019/08/29/232747",
        flex: 6
      },
      {
        title: "タピッカソン",
        src:
          "https://img.supporterzcolab.com/thumbs/94/a2/94a2c74a110247e725123c570459729a.png",
        link: "https://supporterzcolab.com/event/900/",
        description:
          "主催として登録者100名超えのハッカソンの企画から運営、また個人で当日開発して成果発表まで行いました",
        source: "https://github.com/sudo5in5k/tapickathon",
        flex: 6
      },
      {
        title: "PyCon JP 2019",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/3f/a3/3fa3cecce99a41df37a6c762498d62f7.png",
        link: "https://pycon.jp/2019/",
        description:
          "スタッフとして主にスポンサーへの対応やブログ執筆を行いました",
        source: "https://pycon.jp/2019/staff",
        flex: 6
      },
      {
        title: "「〇〇×エンジニア」キャリアパス",
        src:
          "https://connpass-tokyo.s3.amazonaws.com/thumbs/e3/bc/e3bca5d571ac782e9473a5ca049de9f6.png",
        link: "https://kiitok.connpass.com/event/142318/",
        description:
          "kiitok主催のイベントにてブログ枠としてレポート記事を書きました",
        source: "https://ussylog.hatenablog.com/entry/2019/09/17/211516",
        flex: 6
      },
      {
        title: "Kotlin入門",
        src:
          "https://img.supporterzcolab.com/thumbs/0b/46/0b46430d97a328d49c573794868d7db2.png",
        link: "https://supporterzcolab.com/event/949/",
        description: "Javaを使っている方向けのKotlin入門を講義しました",
        source: "https://github.com/sudo5in5k/JavaToKtTrainingForBeginner",
        flex: 6
      },
      {
        title: "ビアッカソン",
        src:
          "https://img.supporterzcolab.com/thumbs/e4/7e/e47ed6869dccf5ebda19c047a964a694.png",
        link: "https://supporterzcolab.com/event/937/",
        description: "主催としてハッカソンの企画から運営ま一貫して行いました",
        source: "https://note.mu/spzcolab/m/m2b98f57c3fc6",
        flex: 6
      },
      {
        title: "DIVE INTO CODE DEMODAY 7th",
        src: "https://i.gyazo.com/1673ca7ba3245c45a26b795392597b05.png",
        link: "https://diveintocode.jp/demoday",
        description: "スポンサーLTとして登壇しました",
        source: "https://speakerdeck.com/sudo5in5k/dive-into-code-demoday-7th",
        flex: 12
      },
      {
        title: "読書会「リーダブルコード」",
        src:
          "https://img.supporterzcolab.com/thumbs/67/80/6780bc7b9d4ac7b0c4791d811eea7e71.png",
        link: "https://supporterzcolab.com/event/958/",
        description: "主催としてABD読書会のファシリテーターを行いました",
        source: "https://speakerdeck.com/sudo5in5k/abddu-shu-hui",
        flex: 6
      },
      {
        title: "pandas入門",
        src:
          "https://img.supporterzcolab.com/thumbs/fd/9e/fd9ea9fa539088adb2f0cdd4789a1c70.png",
        link: "https://supporterzcolab.com/event/971/",
        description: "pandasのデータ加工・整形入門を講義しました",
        source: "https://github.com/sudo5in5k/onlinePandasTutorial",
        flex: 6
      },
      {
        title: "PyCon JP Gihyo",
        src:
          "https://scontent.fkix1-1.fna.fbcdn.net/v/t1.0-9/14233091_10155836011671959_388582903053245335_n.png?_nc_cat=110&_nc_oc=AQlqxyfPNvtyCrM-gLFC-wMdtBD-9Cp0wnrfI0MuBAUuj19v0f-jcJmmMVrjqYgYZ8VxAFm32OjEBvw0oe-_Etl7&_nc_ht=scontent.fkix1-1.fna&oh=c41eef884823cf2e63676dda640c0150&oe=5E16F310",
        link: "https://gihyo.jp/news/report/01/pyconjp2019/0001",
        description:
          "技術評論社にてPyCon JP 2019カンファレンスレポートを執筆をしました",
        source: "",
        flex: 12
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
div.biotext {
  line-height: 2em;
  font-size: large;
}
</style>
