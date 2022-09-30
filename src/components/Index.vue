<script>
export default {
  data: () => {
    return {
      typeValue: '',
      typeStatus: false,
      typeArr: ['학생 개발자입니다.', '프론트엔드 개발자입니다.', '개발을 좋아하는 학생입니다.'],
      typingSpeed: 130,
      erasingSpeed: 110,
      newTextDelay: 2000,
      typeArrIndex: 0,
      charIndex: 0,

      typeValue2: '',
      typeStatus2: false,
      typeArr2: ['이런 사람 입니다.', '이런 것을 좋아합니다.'],
      typingSpeed2: 130,
      erasingSpeed2: 110,
      newTextDelay2: 2000,
      typeArrIndex2: 0,
      charIndex2: 0,

      typeValue3: '',
      typeStatus3: false,
      typeArr3: ['이 언어를 사용합니다.', '이 방식을 선호합니다.'],
      typingSpeed3: 130,
      erasingSpeed3: 110,
      newTextDelay3: 2000,
      typeArrIndex3: 0,
      charIndex3: 0,

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

    typeText2() {
      if (this.charIndex2 < this.typeArr2[this.typeArrIndex2].length) {
        if (!this.typeStatus2) { this.typeStatus2 = true; }

        this.typeValue2 += this.typeArr2[this.typeArrIndex2].charAt(this.charIndex2)
        this.charIndex2 += 1

        setTimeout(this.typeText2, this.typingSpeed2)
      } else { this.typeStatus2 = false; setTimeout(this.eraseText2, this.newTextDelay2) }
    },
    eraseText2() {
      if (this.charIndex2 > 0) {
        if (!this.typeStatus2) { this.typeStatus2 = true }

        this.typeValue2 = this.typeArr2[this.typeArrIndex2].substring(0, this.charIndex2 - 1)
        this.charIndex2 -= 1
        setTimeout(this.eraseText2, this.erasingSpeed2)
      } else {
        this.typeStatus2 = false
        this.typeArrIndex2 += 1
        if (this.typeArrIndex2 >= this.typeArr2.length) {
            this.typeArrIndex2 = 0
        }

        setTimeout(this.typeText2, this.typingSpeed2 + 1000)
      }
    },

    typeText3() {
      if (this.charIndex3 < this.typeArr3[this.typeArrIndex3].length) {
        if (!this.typeStatus3) { this.typeStatus3 = true; }

        this.typeValue3 += this.typeArr3[this.typeArrIndex3].charAt(this.charIndex3)
        this.charIndex3 += 1

        setTimeout(this.typeText3, this.typingSpeed3)
      } else { this.typeStatus3 = false; setTimeout(this.eraseText3, this.newTextDelay3) }
    },
    eraseText3() {
      if (this.charIndex3 > 0) {
        if (!this.typeStatus3) { this.typeStatus3 = true }

        this.typeValue3 = this.typeArr3[this.typeArrIndex3].substring(0, this.charIndex3 - 1)
        this.charIndex3 -= 1
        setTimeout(this.eraseText3, this.erasingSpeed3)
      } else {
        this.typeStatus3 = false
        this.typeArrIndex3 += 1
        if (this.typeArrIndex3 >= this.typeArr3.length) {
            this.typeArrIndex3 = 0
        }

        setTimeout(this.typeText3, this.typingSpeed3 + 1000)
      }
    },

  },
  created() {
    setTimeout(this.typeText, 500)
    setTimeout(this.typeText2, 0)
    setTimeout(this.typeText3, 0)
  }
}
</script>

<template>
  <!-- Index -->
  <img class="h-screen blur-lg brightness-[0.4] fixed -z-10" src="../assets/codebg.png" />
  <div class="h-screen flex justify-center items-center text-white">
    <div class="title text-5xl">저는&nbsp;</div>
    <div class="typed-text text-5xl font-bold">{{ typeValue }}</div>
    <div class="cursor text-5xl w-1 ml-1 font-bold" :class="{'typing': typeStatus}">_</div>
  </div>

  <!-- About -->
  <div class="tln -mt-[100px]"></div>
  <div class="h-screen bg-white flex flex-col justify-center items-center text-black">
    <div class="flex">
      <div class="about-title text-5xl">저는&nbsp;</div>
      <div class="typed-text text-5xl font-bold">{{ typeValue2 }}</div>
      <div class="cursor2 text-5xl w-1 ml-1 font-bold" :class="{'typing2': typeStatus2}">_</div>
    </div>
    <div class="about text-3xl mt-10">
      개발하는 것을 좋아하며 배우는 것을 즐기는 중학생 개발자, <span class="font-bold">손보석</span>입니다.
    </div>
  </div>

  <div class="trn"></div>

  <!-- Spec -->
  <div class="h-screen flex flex-col justify-center items-center text-white">
    <div class="flex">
      <div class="about-title text-5xl">저는 주로&nbsp;</div>
      <div class="typed-text text-5xl font-bold">{{ typeValue3 }}</div>
      <div class="cursor3 text-5xl w-1 ml-1 font-bold" :class="{'typing3': typeStatus3}">_</div>
    </div>

    <div class="flex flex-wrap items-center w-[1024px] mt-10">
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
    <div class="footer text-2xl text-slate-400">ⓒ 2022 dyacode.me. All Rights Reserved.</div>
  </div>
</template>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap');
  .cursor {
    /* display: inline-block; */
    animation: cursorBlink 1s infinite;
  }
  .cursor2 {
    /* display: inline-block; */
    animation: cursorBlink2 1s infinite;
  }
  .cursor3 {
    /* display: inline-block; */
    animation: cursorBlink2 1s infinite;
  }

  .typing {
    animation: none; 
  }
  .typing2 {
    animation: none; 
  }
  .typing3 {
    animation: none; 
  }

  @keyframes cursorBlink {
    49% { color: rgb(218, 218, 218); }
    50% { color: transparent; }
    99% { color: transparent; }
  }
  @keyframes cursorBlink2 {
    49% { color: rgb(218, 218, 218); }
    50% { color: transparent; }
    99% { color: transparent; }
  }
  @keyframes cursorBlink3 {
    49% { color: rgb(218, 218, 218); }
    50% { color: transparent; }
    99% { color: transparent; }
  }

  .tln {
    border-bottom: 0px solid white;
    border-top: 100px solid transparent;
    border-right: 100vw solid white;
    /* border-right: 20px solid transparent; */
  }
  .trn {
    border-bottom: 100px solid transparent;
    border-right: 100vw solid white;
  }
  
</style>