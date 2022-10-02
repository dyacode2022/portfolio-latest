<script>
export default {
  data: () => {
    return {
      typeValue: '',
      typeStatus: false,
      typeArr: ['학생 개발자입니다.', '풀스택 개발자입니다.', '만드는 것을 좋아합니다.'],
      typingSpeed: 130,
      erasingSpeed: 110,
      newTextDelay: 2000,
      typeArrIndex: 0,
      charIndex: 0,
    }
  },
  methods: {
    typeText() {
      if (this.charIndex < this.typeArr[this.typeArrIndex].length) {
        if (!this.typeStatus) { this.typeStatus = true; }

        this.typeValue += this.typeArr[this.typeArrIndex].charAt(this.charIndex)
        this.charIndex += 1

        setTimeout(this.typeText, this.typingSpeed)
      } else { this.typeStatus = false; setTimeout(this.eraseText, this.newTextDelay) }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) { this.typeStatus = true }

        this.typeValue = this.typeArr[this.typeArrIndex].substring(0, this.charIndex - 1)
        this.charIndex -= 1
        setTimeout(this.eraseText, this.erasingSpeed)
      } else {
        this.typeStatus = false
        this.typeArrIndex += 1
        if (this.typeArrIndex >= this.typeArr.length) {
            this.typeArrIndex = 0
        }

        setTimeout(this.typeText, this.typingSpeed + 1000)
      }
    },

  },
  created() {
    setTimeout(this.typeText, 500)
  }
}
</script>

<template>
  <!-- Index -->
  <img class="h-screen blur-lg brightness-[0.4] fixed -z-10" src="../assets/codebg.png" />
  <div class="fxcol h-screen flex justify-center items-center text-white">
    <div class="title text-5xl">저는&nbsp;</div>
    <span class="flex">
      <div class="typed-text text-5xl font-bold">{{ typeValue }}</div>
      <div class="cursor text-5xl w-[1.5px] ml-1 font-bold" :class="{'typing': typeStatus}">&nbsp;</div>
    </span>
  </div>

  <!-- About -->
  <div class="tln -mt-[100px]"></div>
  <div class="h-screen bg-white flex flex-col justify-center items-center text-black">
    <div class="about-title text-5xl font-bold">저는 이런사람입니다.</div>
    <div class="about text-3xl mt-10">
      개발하는 것을 좋아하며 배우는 것을 즐기는 중학생 개발자, <span class="font-bold">손보석</span>입니다.
    </div>
  </div>

  <div class="trn"></div>

  <!-- Spec -->
  <div class="h-screen flex flex-col justify-center items-center text-white">
    <div class="about-title text-5xl font-bold">제가 배운 것들입니다.</div>

    <div class="flex flex-wrap items-center mt-10 md:w-[1024px]">
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/html.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/css.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/js.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/tslogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/ns.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/java.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/pylogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/utlogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/btstlogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/twlogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/vuelogo.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/react.png" />
        <img class="m-5 badge w-20 h-20 hover:brightness-50" src="../assets/lixlogo.png" />
    </div>
  </div>

  <!-- End -->
  <div class="h-screen flex flex-col justify-center items-center text-white">
    <div class="copyright text-2xl text-slate-400">ⓒ 2022 dyacode.me. All Rights Reserved.</div>
  </div>
</template>

<style scoped>
  .cursor {
    display: inline-block;
    animation: cursorBlink 1s infinite;
  }

  .typing {
    animation: none;
    background: white;
  }

  @keyframes cursorBlink {
    0% { background-color: rgb(255, 255, 255); }
    49% { background-color: rgb(255, 255, 255); }
    50% { background-color: transparent; }
    99% { background-color: transparent; }
  }

  .tln {
    border-bottom: 0px solid white;
    border-top: 100px solid transparent;
    border-right: 99vw solid white;
    /* border-right: 20px solid transparent; */
  }
  .trn {
    border-bottom: 100px solid transparent;
    border-right: 99vw solid white;
  }

  @media (max-width: 768px) {

    .cursor {
      visibility: hidden;
    }

    .fxcol {
      display: flex;
      flex-direction: column;
    }

    .title {
      font-size: 30px;
      margin-bottom: 10px;
    }

    .typed-text {
      font-size: 30px;
      padding: 10px;
    }

    .about-title {
      font-size: 35px;
    }

    .about {
      font-size: 25px;
      padding: 30px;
    }

    .copyright {
      font-size: 15px;
    }
  }
  
</style>