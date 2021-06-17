<template>
    <div class="container">
        <b-row>
            <div class="col-md-6 offset-md-3">
                <b-button class="select-btn" @click="sortProjects('all')">All</b-button>
                <b-button class="select-btn" @click="sortProjects('website')">Websites</b-button>
                <b-button class="select-btn" @click="sortProjects('software')">Software</b-button>
            </div>
        </b-row>
        <b-row>
            <b-col class="card-container">
                <div v-for="i in currentProjects" :key="i.name">
                    <ProjectCard :projectData="i" />
                </div>
            </b-col>
        </b-row>
    </div>
</template>

<script>
export default {
    methods: {
        sortProjects(category) {
            switch (category) {
                case "website":
                    this.currentProjects = []

                    this.projects.forEach(element => {
                        if (element.category == "website") {
                            this.currentProjects.push(element)
                        }
                    });

                    break;

                case "software":
                    this.currentProjects = []

                    this.projects.forEach(element => {
                        if (element.category == "software") {
                            this.currentProjects.push(element)
                        }
                    });

                    break;
                default:
                    this.currentProjects = this.projects                        

                    break;
            }
        }
    },
    data() {
        return {
            projects: [
                {
                    name: "AlienLogger",
                    description: "MaaS (Malware as a Service) website offering an easier to use alternative from the traditional keylogger.",
                    image: "https://user-images.githubusercontent.com/29873078/113494787-5b528d80-94f4-11eb-90af-5170fa9b8ff2.png",
                    link: "https://github.com/TasosY2K/Alien-Logger",
                    tech: "NodeJS/Express.js/Python",
                    category: "website" 
                },
                {
                    name: "LitBlog",
                    description: "A minimal portfolio/blog CMS that can be set up in a breeze.",
                    image: "https://camo.githubusercontent.com/240e94d1a14f3f4142f7903cb1a4c609614e89790df9f0265b3bfcbd8056ffac/68747470733a2f2f696d616765732d6578742d312e646973636f72646170702e6e65742f65787465726e616c2f457448354c5042355f67703331426933795a4a616254625a644d39567a6d795f75582d536c6f6d665a57342f68747470732f692e696d6775722e636f6d2f463454677a35362e706e673f77696474683d393334266865696768743d343733",
                    link: "https://github.com/TasosY2K/lit-blog",
                    tech: "NodeJS/Express.js/Webpack",
                    category: "website" 
                },
                {
                    name: "AnonImage",
                    description: "Web app for uploading anonymous password protected and easily shareable images.",
                    image: "https://user-images.githubusercontent.com/29873078/97197071-e09f7c80-17b5-11eb-9c01-b775353f8149.png",
                    link: "https://github.com/TasosY2K/anon-image",
                    tech: "NodeJS/Express.js/Webpack",
                    category: "website" 
                },
                {
                    name: "LightScraper",
                    description: "An optical character recognition search tool for screenshots from prnt.sc.",
                    image: "https://user-images.githubusercontent.com/29873078/73987010-c122a400-4947-11ea-928c-077ef7f8acad.png",
                    link: "https://github.com/TasosY2K/light-scraper",
                    tech: "NodeJS",
                    category: "software" 
                },
                {
                    name: "EspressoBot",
                    description: "HTTP/HTTPS based Golang botnet.",
                    image: "https://user-images.githubusercontent.com/29873078/118262572-bd23f100-b4bd-11eb-9aed-a5b25bdf4d5b.png",
                    link: "https://github.com/TasosY2K/espresso-bot",
                    tech: "NodeJS/Go",
                    category: "software" 
                },
                {
                    name: "ProtonVPN account generator",
                    description: "ProtonVPN account generator.",
                    image: "https://user-images.githubusercontent.com/29873078/78678396-90340080-78f1-11ea-866f-eec2d50771f5.png",
                    link: "https://github.com/TasosY2K/protonvpn-acc-gen",
                    tech: "NodeJS/Puppeteer",
                    category: "software" 
                },
                {
                    name: "LeanTracker",
                    description: "A fast and easy to use ip logger built on express.js.",
                    image: "https://camo.githubusercontent.com/380aee9fcdc46d6f9f5a55279590e77787255df404fc71102b28588bd55455d2/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3630393835343237313831303330363034392f3638383338333036333030343238323930352f53637265656e73686f745f312e706e67",
                    link: "https://lean-tracker-demo.herokuapp.com/",
                    tech: "NodeJS/Express.js",
                    category: "website" 
                },
                {
                    name: "IP Fragment Calculator",
                    description: "An easy to use fragmentation calculator with a web interface.",
                    image: "https://media.discordapp.net/attachments/609854261635055626/855123386887176272/unknown.png?width=1248&height=612",
                    link: "https://kind-ritchie-469952.netlify.app/",
                    tech: "VueJS",
                    category: "website" 
                },
                {
                    name: "ESP8266-Phising",
                    description: "Tactical Phising Attacks with ESP8266.",
                    image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F7%2F7e%2FNodeMCU_DEVKIT_1.0.jpg%2F300px-NodeMCU_DEVKIT_1.0.jpg&f=1&nofb=1",
                    link: "https://github.com/TasosY2K/ESP8266-Phising",
                    tech: "Arduino/HTML/JS",
                    category: "software" 
                },
                {
                    name: "Snappy Short",
                    description: "Snappy Short is a simple but swift link shortener.",
                    image: "https://user-images.githubusercontent.com/29873078/77546483-9f0fc180-6eb4-11ea-9168-df7dfb5b1ec6.png",
                    link: "https://github.com/TasosY2K/snappy-short",
                    tech: "NodeJS/Express.js",
                    category: "website"
                },
                {
                    name: "IP Range Generator",
                    description: "A simple website for creating random fake IP addresses.",
                    image: "https://media.discordapp.net/attachments/609854261635055626/855125827280699392/unknown.png?width=1248&height=612",
                    link: "https://tasosy2k.github.io/Random-IP-Generator",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "Youtube Grabber",
                    description: "YouTube Grabber is a high quality video converter built on express.",
                    image: "https://camo.githubusercontent.com/e3777c6491d6dbcf700e1edc9544fe06526077b9f4b944c7f11a7df69adc0b94/68747470733a2f2f6d656469612e646973636f72646170702e6e65742f6174746163686d656e74732f3630393835343237313831303330363034392f3635353835353838333336383133363731342f53637265656e73686f745f322e706e673f77696474683d373538266865696768743d343235",
                    link: "https://github.com/TasosY2K/youtube-grabber",
                    tech: "NodeJS/Express.js",
                    category: "website"
                },
                {
                    name: "King Crypter Demo Site",
                    description: "Landing page for the upcoming King Crypter project.",
                    image: "https://media.discordapp.net/attachments/609854261635055626/855127912063959060/unknown.png?width=1248&height=612",
                    link: "https://kingcrypter.netlify.app/",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "Digitalza Sec Site",
                    description: "Landing page for my friends at Digitalza Sec.",
                    image: "https://media.discordapp.net/attachments/609854261635055626/855128725368733786/unknown.png?width=1248&height=612",
                    link: "https://digitalza.netlify.app",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "RedBull Basement Vote Bot",
                    description: "A bot for generating fake votes for https://basement.redbull.com/.",
                    image: "https://media.discordapp.net/attachments/609854261635055626/855126318307999754/unknown.png?width=1248&height=612",
                    link: "https://github.com/TasosY2K/basement-bot-votes",
                    tech: "NodeJS/Puppeteer",
                    category: "software"
                },
            ],
            currentProjects: []
        }
    },
    mounted() {
        this.currentProjects = this.projects
    }
}
</script>


<style scoped>
.container {
    text-align: center;
}

.card-container {
    max-width: 1200px;
    margin: 2.7rem auto;
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.select-btn {
    background-color: transparent;
    border-radius: 10px;
    border-color: #f1f1f1;
}

.select-btn:hover {
    background-color: #f1f1f1;
    color: #212121;
    border-color: #212121;
}
</style>