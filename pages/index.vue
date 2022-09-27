<template>
  <div ref="1">
    <div class="section header-section">
      <img src="~/assets/screen.svg" class="header" @click="goto('2')" />
    </div>
    <div ref="2">
      <b-navbar toggleable="lg" class="nav-blue" type="dark" :sticky="true">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#" class="mr-2" @click="goto('1')"
              >Home</b-nav-item
            >
            <b-nav-item href="#" class="mr-2" @click="goto('2')"
              >Skills</b-nav-item
            >
            <b-nav-item href="#" class="mr-2" @click="goto('3')"
              >About</b-nav-item
            >
            <b-nav-item href="#" class="mr-2" @click="goto('4')"
              >Projects</b-nav-item
            >
            <b-nav-item href="#" @click="goto('5')">Contact</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
      <div class="section skills-section">
        <b-container fluid="md">
          <b-row>
            <b-col>
              <img src="~/assets/me.jpg" class="my-image" />
              <h3 class="mt-4">Who am I?</h3>
              <p>
                I am a self-taught web developer/pentester currently studying CS
                in Thessaloniki, GR. I have a serious passion for the cloud and
                the infastructure that powers our everyday lives.
                <a href="javascript:void(0);" @click="goto('5')"
                  >Let's create something special.</a
                >
              </p>
              <a href="https://tryhackme.com/p/leandev" target="_blank" rel="noopener noreferrer">
                 <img src="https://tryhackme-badges.s3.amazonaws.com/leandev.png" alt="TryHackMe">
              </a>
              <a href="/AnastasiosMeletlidisCV.pdf" class="btn cv-btn" download
                >Download CV
                <img
                  style="transform: translateY(-2px)"
                  src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAABmJLR0QA/wD/AP+gvaeTAAAA3ElEQVRIie2Uuw0CMRBEZxGEVHAnaiBGkCASRB80QsSnAPqACmjFZBQAEY8Ag058FnNccAEjbWKv59m7K0t1ENACVsAhxhJoVglY8Kx5GaMJsH9hdlMP6Dv7ARgXPe0BECTlzh0G8czOyQlm1nkHIPm5jszs7tuowtBTrQAbSZmuPdqWojnTAZAV8nIvsewLSukbwBrIgFzSOvVQLcb0KGkmqSupHaMb105fkd/0bOjkjz41OaVEDTN7WTrAJJ0f14slSvlyz7+0plZjWglgX4Fn8ADTHyEhevyVrguoawiwk/2/vAAAAABJRU5ErkJggg=="
              /></a>
            </b-col>
            <b-col>
              <h2 class="skills-header">Skills</h2>
              <div class="skills-container">
                <ProgressBar :percentage="'100%'" :text="'HTML/CSS'" />
                <ProgressBar :percentage="'100%'" :text="'Javascript/NodeJS'" />
                <ProgressBar :percentage="'90%'" :text="'VueJS/NuxtJS'" />
                <ProgressBar :percentage="'90%'" :text="'Python'" />
                <ProgressBar :percentage="'85%'" :text="'AWS/Cloud'" />
                <ProgressBar
                  :percentage="'85%'"
                  :text="'SQL/NoSQL Databases'"
                />
                <ProgressBar :percentage="'90%'" :text="'Golang'" />
                <ProgressBar :percentage="'90%'" :text="'ReactJS/NextJS'" />
                <ProgressBar
                  :percentage="'70%'"
                  :text="'Wordpress/Woocommerce'"
                />
                <ProgressBar :percentage="'70%'" :text="'CS-Cart'" />
                <ProgressBar :percentage="'60%'" :text="'PHP'" />
              </div>
            </b-col>
          </b-row>
        </b-container>
      </div>
      <div class="section about-section" ref="3">
        <b-container fluid="md">
          <b-row>
            <b-col>
              <div class="section-header">About</div>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <img src="~/assets/clock.svg" class="about-icon" />
            </b-col>
            <b-col>
              <img src="~/assets/rocket.svg" class="about-icon mt-2" />
            </b-col>
          </b-row>
          <b-row class="margin-top-fix">
            <b-col>
              <img src="~/assets/device.svg" class="about-icon" />
            </b-col>
            <b-col>
              <img src="~/assets/lamp.svg" class="about-icon mt-2" />
            </b-col>
          </b-row>
        </b-container>
      </div>
      <div class="section projects-section" ref="4">
        <b-container fluid="md">
          <b-row>
            <b-col>
              <div class="section-header text-white">Projects</div>
            </b-col>
          </b-row>
          <b-row>
            <Projects />
          </b-row>
        </b-container>
      </div>
      <div class="section contact-section" ref="5">
        <b-container fluid="md">
          <b-row>
            <b-col>
              <div class="section-header text-white">Contact</div>
            </b-col>
          </b-row>
          <b-row>
            <div class="col-md-6 offset-md-3">
              <b-form-input
                type="text"
                class="contact-form"
                placeholder="Name"
                v-model="emailName"
              ></b-form-input>
              <b-form-input
                type="email"
                class="contact-form mt-3"
                placeholder="E-mail"
                v-model="emailAddress"
              ></b-form-input>
              <b-form-textarea
                class="mt-3 contact-form"
                placeholder="What do you want to build?"
                rows="3"
                max-rows="6"
                v-model="emailContent"
              ></b-form-textarea>
              <button class="submit-btn mt-3" @click="sendWebhook()">
                Send
              </button>
            </div>
          </b-row>
        </b-container>
      </div>
      <div class="footer">
        <span
          >E-mail:
          <a href="mailto:tmeletlidis@protonmail.com"
            >tmeletlidis@protonmail.com</a
          ></span
        >
        |
        <span>Telephone: <a href="tel:+306943804679">+306943804679</a></span>
        <br />
        <a target="_blank" href="https://github.com/TasosY2K/">GitHub</a> -
        <a target="_blank" href="https://www.linkedin.com/in/tasos-meletlidis"
          >LinkedIn</a
        >
      </div>
    </div>
  </div>
</template>

<script>
import ProgressBar from '~/components/ProgressBar.vue'

export default {
  methods: {
    goto(refName) {
      let element = this.$refs[refName]
      let top = element.offsetTop

      window.scrollTo(0, top)
    },
    sendWebhook() {
      let URL = process.env.WEBHOOK_URL
      fetch(URL, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          content: `<@${process.env.DISCORD_ID}>\n**${this.emailName} | ${this.emailAddress}**\n${this.emailContent}`,
        }),
      })
        .then((res) =>
          alert('I will reply to your E-mail address once i get the chance :)')
        )
        .catch((err) => alert(err))
    },
  },
  data() {
    return {
      emailName: '',
      emailAddress: '',
      emailContent: '',
    }
  },
  components: { ProgressBar },
}
</script>

<style>
.nav-blue {
  box-shadow: 0px 8px 30px -5px rgba(0, 0, 0, 0.75);
  font-size: 1.4rem;
  background-color: #001a68;
}

.nav-link {
  color: #f1f1f1 !important;
  border-radius: 30px;
  transition-duration: 0.3s;
  letter-spacing: 1.3px;
}

.nav-link:hover {
  background-color: #ffffff63;
}

@media screen and (max-width: 745px) {
  .nav-link:hover {
    background-color: transparent;
  }
}

.margin-top-fix {
  margin-top: 2.6rem;
}

.header {
  height: 40vh;
  width: auto;
  cursor: pointer;
  user-select: none;
}

@media screen and (max-width: 745px) {
  .header {
    height: 20vh;
  }
}

.section {
  min-height: 100vh;
}

.section-header {
  margin-top: 2rem;
  margin-bottom: 2rem;
  font-size: 3rem;
  color: #173357;
}

.header-section {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: #002490;
}

.about-section {
  text-align: center;
  background-color: #f1f1f1;
  padding-bottom: 2.5rem;
  pointer-events: none;
  user-select: none;
}

.about-icon {
  height: 35vh;
  width: auto;
}

@media screen and (max-width: 745px) {
  .about-icon {
    height: 30vh;
  }
}

.skills-section {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.my-image {
  height: 30vh;
  width: auto;
  border-radius: 50%;
}

@media screen and (max-width: 745px) {
  .my-image {
    height: 20vh;
    margin-top: 3rem;
  }
}

.cv-btn {
  background-color: rgb(0, 202, 108);
  color: #f1f1f1;
  border-radius: 30px;
  font-size: 1.2rem;
  transition-duration: 0.3s;
}

.cv-btn:hover {
  color: #f1f1f1;
  box-shadow: 0px 8px 30px -5px rgba(0, 187, 100, 0.75);
}

.skills-container {
  text-align: left;
}

.skills-header {
  color: #173357;
}

@media screen and (max-width: 745px) {
  .skills-header {
    margin-top: 3rem;
  }
}

.projects-section {
  text-align: center;
  background-color: #002490;
}

.contact-section {
  text-align: center;
  background-color: #001336;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.contact-form {
  background-color: #000d23;
  transition-duration: 0.3s;
  border-radius: 10px;
  overflow: hidden !important;
  color: #f1f1f1;
}

.contact-form:hover,
.contact-form:focus {
  color: #f1f1f1;
  background-color: #01173d;
}

.submit-btn {
  transition-duration: 0.3s;
  border-radius: 30px;
  padding: 7px 2rem 7px 2rem;
  color: #f1f1f1;
  border: none;
  background-color: rgb(3, 82, 172);
}

.submit-btn:hover {
  background-color: rgb(3, 98, 206);
  box-shadow: 0px 4px 18px -4px rgba(3, 98, 206, 0.75);
}

.footer {
  padding: 1.5rem 0 1.5rem 0;
  text-align: center;
  background-color: #000d23;
  color: #f1f1f1;
}

.footer > a,
.footer > span > a {
  color: rgb(0, 202, 108);
}
</style>
