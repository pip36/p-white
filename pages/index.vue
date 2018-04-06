<template>
  <section class="container">
    <div class="main">
      <h1 class="title">
        Phil White
      </h1>
      <h2 class="subtitle">
        phil_23@live.co.uk
      </h2>

      <div :class="{'info': true, 'info-container-center': !aboutActive}" >
        <div class="image-container">
          <img class="profile-pic" src="/profpic1.png"/>
        </div>
        <transition name="fade">
          <div class="text" v-show="aboutActive">    
            <p>
              I'm a musician and aspiring web developer currently based near Cardiff.
              My main instrument of choice is the oboe, 
              <a href="https://www.urbandictionary.com/define.php?term=oboe" target="_blank"> (What's an oboe?) </a>,
              and when it comes to code I'm currently favouring vue js framework and node, although I've dabbled in
              ruby on rails, and also C# within the unity game framework.
              <br><br>
              I keep most of my projects within github, which you can visit below, and a selection of these projects 
              are up and running from the projects page.
              <br><br>
              Please feel free to contact me about any web development opportunities via email at the top of the page, 
              or if you have a question to ask.
            </p>  
          </div>
        </transition>
      </div>

      <div class="links">
        <a
          href="https://github.com/pip36"
          target="_blank"
          class="button--grey">GitHub <i class="fab fa-github"></i> </a>
       <a class="button--grey" @click="toggleAboutInfo()"> About </a>
       
      </div>
      <br>
      <a class="button--grey" @click="slideToBottom()"> Projects </a>    
    </div>
    <div class="projects">
      <carousel/>
    </div>
    
  </section>
</template>

<script>
import smoothscroll from 'smoothscroll-polyfill'
import AppLogo from '~/components/AppLogo.vue'
import Carousel from '~/components/Carousel.vue'

export default {
  components: {
    AppLogo,
    Carousel
  },
  data () {
    return {
      aboutActive: false
    }
  },
  mounted () {
    smoothscroll.polyfill()
  },
  methods: {
    slideToBottom () {
      window.scroll({
        top: document.body.scrollHeight,
        behavior: 'smooth'
      })    
    },

    toggleAboutInfo () {
      this.aboutActive ? this.aboutActive = false : this.aboutActive = true
    }
  }
}
</script>

<style scoped>
.container {
  min-height: 200vh;
}

.main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.projects {
  height: 100vh;
  background: linear-gradient(white, rgb(166, 182, 255))
}


.links {
  padding-top: 15px;
}

.info {
  display:inline-flex;
  transition: transform 0.5s, margin-right 0.5s;
  padding: 5px;
  max-width: 1000px;
}

.text {
  padding-left: 5px;
  padding-right: 5px;
}



.fade-enter-active {
  transition: opacity 0.5s 0.5s;
}
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

</style>
