<template>
  <v-container
    fluid
    class="d-flex justify-center bg-teal-lighten-4 py-16 h-100"
  >
    <v-card
      :color="$route.query.rgb"
      class="my-card rounded-lg elevation-10 overlay"
      style="max-width: 360px; max-height: 480px"
    >
      <div class="mx-8 my-3 text-h6 font-weight-bold">
        {{ $route.query.name }}
      </div>
      <v-sheet class="justify-center mx-8" :color="$route.query.rgb">
        <v-img
          v-if="$route.query.avatar == '1'"
          class="rounded-lg border-sm"
          src="https://th.bing.com/th/id/OIP.uHXyBOA1mX-KQGcQtbActAHaE8?rs=1&pid=v-ImgDetMain"
          :width="600"
          :height="200"
        />
        <v-img
          v-if="$route.query.avatar == '2'"
          style="border: 1px white"
          class="rounded-lg"
          src="https://i.namu.wiki/i/7dnnR9fpmkY0JIjO4JSj6rOnJ75BmryAXDnUI1cUMTy_JGxV2z6TyazRU9WJziM9k0Sl1JCjBwk7dBYiNvPh-Q.webp"
          :width="600"
          :height="200"
        />
        <v-img
          v-if="$route.query.avatar == '3'"
          style="border: 1px white"
          class="rounded-lg"
          src="https://image.newsis.com/2023/07/12/NISI20230712_0001313626_web.jpg"
          :width="600"
          :height="200"
        />
        <v-img
          v-if="$route.query.avatar == '4'"
          style="border: 1px white"
          class="rounded-lg"
          src="https://mblogthumb-phinf.pstatic.net/MjAxNzAxMjVfMjYz/MDAxNDg1MzQ5NjIxMDk2.LoOsq-oSKIn8NXlulM_4-IiNogTFTTZCwMiOCy1e154g.m7bYXYxlfqBvg9VM1MHqzaWqf1elVpakw_sJYZ5_c4gg.PNG.oyaubihime/025Pikachu_OS_anime_11.png?type=w800"
          :width="600"
          :height="200"
        />
        <v-img
          v-if="$route.query.avatar == '5'"
          src="https://www.nintendo.co.kr/character/kirby/assets/img/intro/kirby-star2.png"
          style="border: 1px white"
          class="rounded-lg"
          :width="600"
          :height="200"
        />
      </v-sheet>
      <div class="my-8"></div>
      <v-sheet
        class="mx-8 pa-2 rounded border bg-white opacity-60"
        style="height: 160px"
      >
        <div class="my-1 text-subtitle-1">
          age: &nbsp {{ $route.query.age }}
        </div>

        <div class="my-1 text-subtitle-1">
          job: &nbsp {{ $route.query.job }}
        </div>

        <div class="my-1 text-subtitle-1">
          hobby: &nbsp {{ $route.query.hobby }}
        </div>

        <div class="my-1 text-subtitle-1">
          mbti: &nbsp {{ $route.query.mbti }}
        </div>
      </v-sheet>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "Query",
  setup() {
    // var container = document.querySelector(".container");
    // var overlay = document.querySelector(".overlay");

    // container.addEventListener("mousemove", function (e) {
    //   var x = e.offsetX;
    //   var y = e.offsetY;
    //   var rotateY = (-1 / 5) * x + 20;
    //   var rotateX = (4 / 30) * y - 20;

    //   overlay.style = `background-position : ${
    //     x / 5 + y / 5
    //   }%; filter : opacity(${x / 200}) brightness(1.2)`;

    //   container.style = `transform : perspective(350px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
    // });

    // container.addEventListener("mouseout", function () {
    //   overlay.style = "filter : opacity(0)";
    //   container.style =
    //     "transform : perspective(350px) rotateY(0deg) rotateX(0deg)";
    // });
    return {
      // container,
      // overlay,
    };
  },
};
</script>
<style>
.overlay {
  position: absolute;
  background: linear-gradient(
    105deg,
    transparent 40%,
    rgba(255, 219, 112, 0.8) 45%,
    rgba(132, 50, 255, 0.6) 50%,
    transparent 54%
  );
  filter: brightness(1.1) opacity(0.8);
  mix-blend-mode: color-dodge;
  background-size: 150% 150%;
  background-position: 100%;
  transition: all 0.1s;
}
</style>
