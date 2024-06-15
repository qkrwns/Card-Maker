<template>
  <div class="bg-indigo-lighten-1" style="min-width: 360px">
    <v-container>
      <v-row class="flex justify-center">
        <v-col cols="8">
          <div
            style="color: red"
            class="hidden-sm-and-down title rounded-lg my-10 text-h3 font-weight-black text-center bg-blue-grey-lighten-5 pa-3 color-red"
          >
            self-introduction business card making page
          </div>
          <div
            style="color: red"
            class="hidden-md-and-up title rounded-lg my-10 text-h3 font-weight-black text-center bg-blue-grey-lighten-5 pa-3 color-red"
          >
            self-introduction business card making page
          </div>
          <v-sheet
            class="py-10 px-16 rounded-lg elevation-6 bg-blue-grey-lighten-5"
          >
            <div class="text-h5 font-weight-bold">Name</div>
            <v-text-field
              variant="outlined"
              class="mt-5"
              type="text"
              v-model="name"
            >
            </v-text-field>
            <div class="mt-10 text-h5 font-weight-bold">Age</div>
            <v-text-field
              variant="outlined"
              class="mt-5"
              type="number"
              v-model="age"
            >
            </v-text-field>
            <div class="mt-10 text-h5 font-weight-bold">Job</div>
            <v-text-field
              variant="outlined"
              class="mt-5"
              type="text"
              v-model="job"
            ></v-text-field>
            <div class="mt-10 text-h5 font-weight-bold">Hobby</div>
            <v-text-field
              variant="outlined"
              class="mt-5"
              type="text"
              v-model="hobby"
            ></v-text-field>
            <div class="mt-10 text-h5 font-weight-bold">MBTI</div>
            <v-text-field
              variant="outlined"
              class="mt-5"
              type="text"
              v-model="mbti"
            ></v-text-field>
            <div class="mt-10 text-h5 font-weight-bold">Favorite Color</div>
            <div class="mt-5 rounded">
              <input
                style="width: 100%; height: 60px"
                type="color"
                v-model="rgbHex"
              />
            </div>
            <div class="mt-10 text-h5 font-weight-bold">Profile</div>
            <v-row>
              <v-col>
                <v-sheet
                  class="d-flex justify-center mt-6 bg-blue-grey-lighten-5"
                >
                  <v-avatar
                    size="80"
                    image="https://th.bing.com/th/id/OIP.uHXyBOA1mX-KQGcQtbActAHaE8?rs=1&pid=ImgDetMain"
                  />
                </v-sheet>
                <v-btn block class="bg-indigo mt-5" @click="setAvatar('1')"
                  >1</v-btn
                >
              </v-col>
              <v-col>
                <v-sheet
                  class="d-flex justify-center mt-6 bg-blue-grey-lighten-5"
                >
                  <v-avatar
                    size="80"
                    class="mx-4"
                    image="https://i.namu.wiki/i/7dnnR9fpmkY0JIjO4JSj6rOnJ75BmryAXDnUI1cUMTy_JGxV2z6TyazRU9WJziM9k0Sl1JCjBwk7dBYiNvPh-Q.webp"
                  />
                </v-sheet>
                <v-btn block class="bg-indigo mt-5" @click="setAvatar('2')"
                  >2</v-btn
                >
              </v-col>
              <v-col>
                <v-sheet
                  class="d-flex justify-center mt-6 bg-blue-grey-lighten-5"
                >
                  <v-avatar
                    size="80"
                    class="mx-4"
                    image="https://image.newsis.com/2023/07/12/NISI20230712_0001313626_web.jpg"
                  />
                </v-sheet>
                <v-btn block class="bg-indigo mt-5" @click="setAvatar('3')"
                  >3</v-btn
                >
              </v-col>
              <v-col>
                <v-sheet
                  class="d-flex justify-center mt-6 bg-blue-grey-lighten-5"
                >
                  <v-avatar
                    size="80"
                    class="mx-4"
                    image="https://mblogthumb-phinf.pstatic.net/MjAxNzAxMjVfMjYz/MDAxNDg1MzQ5NjIxMDk2.LoOsq-oSKIn8NXlulM_4-IiNogTFTTZCwMiOCy1e154g.m7bYXYxlfqBvg9VM1MHqzaWqf1elVpakw_sJYZ5_c4gg.PNG.oyaubihime/025Pikachu_OS_anime_11.png?type=w800"
                  />
                </v-sheet>
                <v-btn block class="bg-indigo mt-5" @click="setAvatar('4')"
                  >4</v-btn
                >
              </v-col>
              <v-col>
                <v-sheet
                  class="d-flex justify-center mt-6 bg-blue-grey-lighten-5"
                >
                  <v-avatar
                    size="80"
                    class="mx-4"
                    image="https://www.nintendo.co.kr/character/kirby/assets/img/intro/kirby-star2.png"
                  />
                </v-sheet>
                <v-btn block class="bg-indigo mt-5" @click="setAvatar('5')"
                  >5</v-btn
                >
              </v-col>
            </v-row>
          </v-sheet>

          <div @click="set_info">
            <ul>
              <router-link
                :to="{
                  name: 'Query',
                  query: {
                    name: name,
                    age: age,
                    job: job,
                    hobby: hobby,
                    rgb: rgbHex,
                    mbti: mbti,
                    avatar: avatar,
                  },
                }"
              >
                <v-btn
                  block
                  class="bg-success py-8 text-h5 font-weight-bold mt-5 elevation-6"
                >
                  Apply
                </v-btn>
              </router-link>
            </ul>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
import { ref } from "vue";
import CustomButton from "@/components/CustomButton.vue";

export default {
  setup() {
    const name = ref("default");
    const age = ref(0);
    const rgbHex = ref("#ffffff");
    const job = ref("default");
    const hobby = ref("default");
    const mbti = ref("ENFP");
    const avatar = ref("1");

    const setAvatar = (n) => {
      avatar.value = n;
    };

    return {
      name,
      age,
      job,
      hobby,
      rgbHex,
      mbti,
      avatar,
      setAvatar,
    };
  },
};
</script>
<style>
.title {
  font: italic small-caps bold 16px/2 cursive;
}
</style>
