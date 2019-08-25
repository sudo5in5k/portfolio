<template>
  <v-app>
    <!-- Header -->
    <v-app-bar app fixed>
      <v-toolbar-title class="headline">
        <span class="font-weight-light">Ussy's portfolio</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        v-for="(next, i) in headerItems"
        :key="i"
        :href="next.href"
        class="my-2"
      >{{ next.text }}</v-btn>
    </v-app-bar>

    <!-- Content -->
    <v-content>
      <HelloWorld />
    </v-content>

    <!-- Footer -->
    <v-footer height="auto" dark padless>
      <v-card class="flex flat tile">
        <v-card-title class="teal">
          <div class="my-2">Contact</div>
        </v-card-title>

        <v-container fluid>
          <v-row>
            <v-col cols="12">
              <v-row justify="center">
                <v-card :loading="loading" class="transparent my-12" flat max-width="400">
                  <v-img :src="require('@/assets/contact.jpg')" />
                </v-card>
                <v-card :loading="loading" class="transparent my-4" flat>
                  <v-card-text class="font-weight-bold white--text my-6 mx-4">
                    <div class="biotext" style="white-space:pre-line">
                      <li>
                        <a href="https://supporterzcolab.com/">勉強会の講師を募集</a> (インセンティブあり)
                      </li>
                      <li>
                        <a href="https://focus.voyagegroup.com/post-0007/">エンジニアの皆様向けの勉強会の会場提供</a>
                      </li>
                      <li>その他ご依頼・ご相談</li>
                    </div>

                    <div class="biotext mx-6 my-2" style="white-space:pre-line">がございましたら下記宛先へご連絡ください</div>
                    <div
                      class="biotext mx-6"
                      style="white-space:pre-line"
                    >E-mail: sudo5in5k★gmail.com (★を直してください)</div>
                    <div class="biotext mx-6">
                      Twitter DM:
                      <a href="https://twitter.com/shoushi12">@shoushi12</a>
                    </div>
                  </v-card-text>
                </v-card>
              </v-row>
            </v-col>
          </v-row>
        </v-container>

        <v-divider></v-divider>

        <v-card-actions class="justify-center">{{ new Date().getFullYear() }} - Ussy</v-card-actions>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
export default {
  name: "App",
  components: {
    HelloWorld
  },
  data: () => ({
    headerItems: [
      {
        text: "Home",
        href: "#"
      },
      {
        text: "Skill",
        href: "#skills"
      },
      {
        text: "Career",
        href: "#career"
      },
      {
        text: "Activity",
        href: "#activity"
      }
    ]
  })
};
</script>