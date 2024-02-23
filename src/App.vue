<template>
  <div>
    <full-page ref="fullpage" :options="options" id="fullpage">
      <!-- 第一頁 -->
      <div class="section">
        <div class="background first">
          <img id="weddingInvitation" class="zoom-in" src="./assets/images/weddingInvitation.png"
            alt="weddingInvitation" />
          <img id="bird" src="./assets/images/bird.png" alt="bird" />
          <img id="butterfly1" src="./assets/images/butterfly1.png" alt="butterfly1" />
          <img id="butterfly2" src="./assets/images/butterfly2.png" alt="butterfly2" />
        </div>
      </div>
      <!-- 第二頁 -->
      <div class="section">
        <div class="background second">
          <div class="info">
            <img id="xi" class="zoom-in" src="./assets/images/xi.png" alt="xi" />
            <!-- 上方資訊 -->
            <div class="top">
              <!-- 人員 -->
              <div class="people">
                <div>
                  <div class="bold">新郎</div>
                  <div class="name">陳暘<img src="./assets/images/Yang.svg" alt="yang" /></div>
                  <div class="bold mgt-8">男方家長</div>
                  <div class="name">陳永春</div>
                  <div class="name">方淑芳</div>
                </div>
                <div>
                  <div class="bold">新娘</div>
                  <div class="name">袁涵萱<img src="./assets/images/Marie.svg" alt="marie" /></div>
                  <div class="bold mgt-8">女方家長</div>
                  <div class="name">袁世富</div>
                </div>
              </div>
            </div>
            <!-- 地點 -->
            <div class="bottom bold">
              <p>
                2024.03.16 (六)<br />
                16:30 證婚儀式<br />
                17:00 迎賓酒會<br />
                18:00 婚禮饗宴
              </p>
              <div class="divider" />
              <p>
                香草菲菲<br />
                宜蘭縣員山鄉內城路650號<br />
                03 922 9933
              </p>
            </div>
            <!-- 下方交通資訊 -->
            <!-- <div class="bottom">
              <div class="title bold">交通資訊</div>
              <p>
                <span class="bold">【大眾運輸】</span><br />
                1.於宜蘭火車站搭乘752公車（開往台北榮總員山分院），於榮光路站下車步行前往約十四分鐘即可抵達。<br />
                2.於宜蘭火車站搭乘1786.1743公車，於下深溝站下車步行前往約九分鐘即可抵達。
              </p>
              <p>
                <span class="bold">【自行開車】</span><br />
                國道五號下宜蘭交流道（壯圍／宜蘭出口），走192縣道至大福路二段左轉中山路五段，再右轉接環河路，續接員山路一段，大鬮路右轉，接內城路即可抵達。
              </p>
            </div> -->
          </div>
          <img class="talk-l" src="./assets/images/bg_2_talk_l.png" alt="" />
          <img class="talk-r" src="./assets/images/bg_2_talk_r.png" alt="" />
          <img class="corner-l" src="./assets/images/bg_2_flower_l.png" alt="" />
          <img class="corner-r" src="./assets/images/bg_2_flower_r.png" alt="" />
        </div>
      </div>
      <!-- 第三頁 -->
      <div class="section">
        <div class="background third">
          <div class="frame-pic1">
            <img src="./assets/images/frame_1.png" alt="" />
            <img class="corner" src="./assets/images/frame_1_flower.png" alt="" />
          </div>
          <div class="couple1">
            <div>
              <img class="" src="./assets/images/couple_1.png" alt="couple_1" />
              <img class="" src="./assets/images/couple_flower_1.png" alt="flowerGroup_1" />
            </div>
          </div>
          <div class="couple2">
            <div>
              <img class="" src="./assets/images/couple_2.png" alt="couple_2" />
              <img class="" src="./assets/images/couple_flower_2.png" alt="flowerGroup_2" />
            </div>
          </div>
        </div>
      </div>
      <!-- 第四頁 -->
      <div class="section">
        <div class="background forth">
          <img class="thanks" src="./assets/images/thankYou.png" alt="thankYou" />
          <div class="frame-pic2">
            <img src="./assets/images/frame_2.png" alt="" />
            <img class="border-r" src="./assets/images/frame_2_img_1.png" alt="" />
            <img class="border-l" src="./assets/images/frame_2_img_2.png" alt="" />
          </div>
          <img class="bottom-flower-group" src="./assets/images/bg_4_flower.png" alt="" />
        </div>
      </div>
    </full-page>
    <img v-if="!isLast" src="./assets/images/arrow.svg" alt="" class="arrow">
  </div>
</template>

<script setup>
import ScrollMagic from 'scrollmagic'
import { onMounted, ref } from 'vue'

const isLast = ref(false)

const handleAfterLoad = (origin, destination, direction, trigger) => {
  isLast.value = destination.isLast
}

const options = {
  // licenseKey: 'KEY',
  onLeave: handleAfterLoad,
  scrollOverflow: false,
  scrollBar: false,
  // anchors: ['home', 'info', 'highlights', 'thanku'],
}

onMounted(() => {
  const controller = new ScrollMagic.Controller()
  // build scenes
  new ScrollMagic.Scene({ triggerElement: ".first" })
    .setClassToggle(".first", "loaded")
    .addTo(controller)
  new ScrollMagic.Scene({ triggerElement: ".second" })
    .setClassToggle(".second", "loaded")
    .addTo(controller)
  new ScrollMagic.Scene({ triggerElement: ".third" })
    .setClassToggle(".third", "loaded")
    .addTo(controller)
  new ScrollMagic.Scene({ triggerElement: ".forth" })
    .setClassToggle(".forth", "loaded")
    .addTo(controller)
});

</script>

<style scoped lang="scss">
@keyframes up {
  0% {
    -webkit-transform: translateY(0px);
    transform: translateY(0px);
    opacity: 1
  }

  50% {
    -webkit-transform: translateY(-10px);
    transform: translateY(-10px);
    opacity: 0.5
  }

  100% {
    opacity: 0
  }
}

@mixin narrow-mobile {

  /* 適配窄螢幕裝置 */
  @media(max-width: 320px) {
    @content;
  }
}

%zoom-in {
  opacity: 0;
  transform: scale3d(0.3, 0.3, 0.3);
  transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
}

%zoom-in-visible {
  opacity: 1;
  transform: scale3d(1, 1, 1);
  transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.arrow {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 8%;
  opacity: 0.6;
  position: absolute;
  bottom: 3px;
  left: 0;
  right: 0;
  margin: auto;
  transition: all 2s ease;
  -webkit-animation: up 1s linear infinite;
  -moz-animation: up 1s linear infinite;
  -o-animation: up 1s linear infinite;
  animation: up 1s linear infinite;
}

.background {
  width: 100%;
  height: 100%;

  &.first {
    background: url('./assets/images/bg_1.png') top/cover no-repeat;
    text-align: center;

    #weddingInvitation {
      margin-top: 155px;
      width: 83%;
      height: auto;
      object-fit: contain;
      @extend %zoom-in
    }

    #bird {
      position: absolute;
      top: 320px;
      left: -28%;
      width: 28%;
      height: auto;
      object-fit: contain;
    }

    #butterfly1 {
      position: absolute;
      bottom: 0;
      left: 0;
      transform: scale3d(0.3, 0.3, 0.3);
      width: 40px;
      height: auto;
      transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
      opacity: 0;
    }

    #butterfly2 {
      position: absolute;
      bottom: 0;
      right: 0;
      transform: scale3d(0.1, 0.1, 0.1);
      width: 56px;
      height: auto;
      transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
      opacity: 0;
    }

    &.loaded {
      #weddingInvitation {
        @extend %zoom-in-visible
      }

      #bird {
        opacity: 1;
        top: 226px;
        left: 10%;
        transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
        transition-delay: .6s;
      }

      #butterfly1 {
        opacity: 1;
        bottom: 2%;
        left: 8%;
        transform: scale3d(1, 1, 1);
        transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
        transition-delay: 1.2s;
      }

      #butterfly2 {
        opacity: 1;
        bottom: 7%;
        right: 14%;
        transform: scale3d(1, 1, 1);
        transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
        transition-delay: 1.3s;
      }
    }
  }

  &.second {
    background: url('./assets/images/bg_2.png') top/cover no-repeat;

    #xi {
      position: absolute;
      width: 206px;
      height: auto;
      object-fit: contain;
      z-index: 0;
      @extend %zoom-in
    }

    .talk {
      &-l {
        position: absolute;
        top: 220px;
        left: 30px;
        width: 106px;
        height: auto;
        object-fit: contain;
        @extend %zoom-in
      }

      &-r {
        position: absolute;
        top: 330px;
        right: 40px;
        width: 102px;
        height: auto;
        object-fit: contain;
        @extend %zoom-in
      }
    }

    .corner {
      &-l {
        position: absolute;
        bottom: -10%;
        left: -20%;
        width: 142px;
        height: auto;
        object-fit: contain;
        @extend %zoom-in;
      }

      &-r {
        position: absolute;
        bottom: -10%;
        right: -20%;
        width: 142px;
        height: auto;
        object-fit: contain;
        @extend %zoom-in;
      }
    }

    &.loaded {
      #xi {
        @extend %zoom-in-visible;
      }

      .talk {
        &-l {
          @extend %zoom-in-visible;
          transition-delay: 1s;
          transition-duration: 1.5s;
          top: 250px;
          left: 90px;
        }

        &-r {
          @extend %zoom-in-visible;
          transition-delay: 1.4s;
          transition-duration: 1.8s;
          top: 280px;
          right: 100px;
        }
      }

      .corner {
        &-l {
          @extend %zoom-in-visible;
          transition-delay: .4s;
          transition-duration: 1.8s;
          bottom: 0;
          left: 0;
        }

        &-r {
          @extend %zoom-in-visible;
          transition-delay: .5s;
          transition-duration: 1.8s;
          bottom: 0;
          right: 0;
        }
      }
    }

    .info {
      height: 100%;
      padding: 85px 12px 16px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      text-align: center;
      font-weight: 500;
      font-size: 14px;

      p {
        font-weight: 500;
      }

      .bold {
        font-weight: 700;
      }

      .mgt-8 {
        margin-top: 8px;
      }

      .top {
        padding: 0 8%;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        z-index: 1;

        .people {
          display: flex;
          justify-content: space-between;
          width: 100%;

          >div {
            flex: 1 0 50%;
          }

          .name {
            font-size: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            white-space: nowrap;

            >img {
              width: auto;
              height: 20px;
              object-fit: contain;
              margin-left: 4px;
            }
          }
        }
      }

      .bottom {
        font-size: 16px;

        .divider {
          height: 1px;
          background-color: rgba(217, 217, 217, .5);
          margin: 12px 0;
        }
      }
    }
  }

  &.third {
    background: url('./assets/images/bg_3.png') top/cover no-repeat;

    .frame-pic1 {
      position: relative;
      padding: 36px 16px;

      >img {
        width: 100%;
        height: auto;
        object-fit: contain;
      }

      .corner {
        position: absolute;
        top: 33px;
        right: 0;
        width: 155px;
        height: auto;
        object-fit: contain;
        @extend %zoom-in
      }
    }

    .couple {
      &1 {
        position: absolute;
        left: -35px;
        bottom: 16%;

        >div {
          position: relative;
          width: 213px;
          height: 287px;

          >img:first-child {
            position: absolute;
            top: 0;
            right: 0;
            width: 203px;
            height: 203px;
            object-fit: contain;
            z-index: 1;

            // @include narrow-mobile {
            //   width: 180px;
            //   height: 180px;
            // }
          }

          >img:nth-child(2) {
            position: absolute;
            bottom: 0;
            left: 3px;
            width: 209px;
            height: 163px;
            object-fit: contain;
            z-index: 2;
            @extend %zoom-in;

            // @include narrow-mobile {
            //   bottom: 80px;
            //   left: 6px;
            //   width: 181px;
            // }
          }
        }
      }

      &2 {
        position: absolute;
        right: -59px;
        bottom: 8px;

        >div {
          position: relative;
          width: 267px;
          height: 307px;

          >img:first-child {
            position: absolute;
            top: 0;
            left: 0;
            width: 259px;
            height: 259px;
            object-fit: contain;

            // @include narrow-mobile {
            //   top: 72px;
            //   left: 63px;
            //   width: 256px;
            //   height: 256px;
            // }
          }

          >img:nth-child(2) {
            position: absolute;
            bottom: 0;
            left: -5px;
            width: 267px;
            height: 186px;
            object-fit: contain;
            @extend %zoom-in;

            // @include narrow-mobile {
            //   bottom: 28px;
            //   left: 88px;
            //   width: 180px;
            // }
          }
        }
      }
    }

    &.loaded {
      .frame-pic1 .corner {
        @extend %zoom-in-visible;
        transition-delay: .2s;
        transition-duration: 1.2s;
      }

      .couple1>div>img:nth-child(2) {
        @extend %zoom-in-visible;
        transition-delay: .4s;
        transition-duration: 1.8s;
      }

      .couple2>div>img:nth-child(2) {
        @extend %zoom-in-visible;
        transition-delay: .6s;
        transition-duration: 2s;
      }
    }
  }

  &.forth {
    background: url('./assets/images/bg_3.png') bottom/cover no-repeat;
    text-align: center;

    .thanks {
      margin-top: 6%;
      width: 65%;
      height: auto;
      object-fit: contain;
      @extend %zoom-in;
    }

    .frame-pic2 {
      position: relative;
      width: 46vh;
      max-width: calc(100% - 24px);
      margin: auto;

      >img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }

      .border-r {
        position: absolute;
        bottom: 0;
        right: -38%;
        width: 175px;
        height: auto;
        object-fit: contain;
      }

      .border-l {
        position: absolute;
        top: 15%;
        left: -28%;
        width: 127px;
        height: auto;
        object-fit: contain;
      }
    }

    .bottom-flower-group {
      position: absolute;
      bottom: -25%;
      left: 0;
      width: 100%;
      height: auto;
      object-fit: contain;
      @extend %zoom-in;
    }

    &.loaded {
      .thanks {
        @extend %zoom-in-visible;
        transition-delay: .1s;
      }

      .frame-pic2 {
        .border-r {
          @extend %zoom-in-visible;
          right: -18%;
          transition-delay: .2s;
          transition-duration: 1.6s;
        }

        .border-l {
          @extend %zoom-in-visible;
          top: 28%;
          left: -45px;
          transition-delay: .2s;
          transition-duration: 1.7s;
        }
      }

      .bottom-flower-group {
        @extend %zoom-in-visible;
        bottom: -8px;
        transition-delay: .3s;
        transition-duration: 1.8s;
      }
    }
  }
}

:deep(.fp-watermark) {
  display: none;
}

@media (min-width: 1024px) {}
</style>
