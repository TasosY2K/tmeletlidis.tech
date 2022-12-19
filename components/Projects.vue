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
                    name: "Penetration testing tool for web cams",
                    description: "A tool meant to assist cyber security researchers on discovering outdated and vulnerable camera systems on the internet by utilizing shodan.io",
                    image: "https://user-images.githubusercontent.com/29873078/208548162-70f5111e-609e-4687-968c-6e3d6cf322d3.png",
                    link: "https://observablehq.com/@tasos/hegemony",
                    tech: "JS/d3/Plotly/ObservableHQ",
                    category: "website" 
                },
                {
                    name: "Plug and Plot",
                    description: "(Google Summer of Code 2022) Reusable visualizations for AS-hegemony data",
                    image: "https://user-images.githubusercontent.com/29873078/208547884-e70f396a-44d9-4cf0-afb5-096fbc4fec5f.png",
                    link: "https://github.com/TasosY2K/camera-exploit-tool",
                    tech: "Python/SQLite",
                    category: "software" 
                },
                {
                    name: "ClinApp Dashboard",
                    description: "Dashboard for https://clinapp.gr/ (appointment management and prediction/medical data collection app)",
                    image: "https://user-images.githubusercontent.com/29873078/208547395-7f85a3cb-7b1c-45a9-8eaa-42b01ed05bcc.png",
                    link: "https://clinapp.csd.auth.gr",
                    tech: "ReactJS",
                    category: "website" 
                },
                {
                    name: "Incentive Toolkit",
                    description: "Resources for Inspiring & Supporting Citizen Science Hubs",
                    image: "https://user-images.githubusercontent.com/29873078/192585538-d6db48b6-c4ab-4fdb-a209-853117977b51.png",
                    link: "https://toolkit.incentive-project.eu/",
                    tech: "ReactJS/Flask",
                    category: "website" 
                },
                {
                    name: "The Ukraine Data Observatory",
                    description: "Platform for analyzing and visualizing data related to the war between Ukraine and Russia",
                    image: "https://user-images.githubusercontent.com/29873078/192586192-104debd7-5d21-4e02-a4f9-9ea100b3ac61.png",
                    link: "https://undo.csd.auth.gr/home",
                    tech: "ReactJS/Flask",
                    category: "website" 
                },
                {
                    name: "Bit Warriors web services",
                    description: "Suite of custom self-hosted web services for my CTF team",
                    image: "https://user-images.githubusercontent.com/29873078/154498925-c1013115-5582-461a-82e1-162ee878d5d4.png",
                    link: "https://bitwarriors.net/",
                    tech: "VueJS/NodeJS",
                    category: "website" 
                },
                {
                    name: "Bot Detective",
                    description: "AI powered web app for in-depth analysis of twitter accounts",
                    image: "https://user-images.githubusercontent.com/29873078/154498932-e1597697-3599-4dba-8c1f-7a0e4b15bc52.png",
                    link: "http://bot-detectivev2.csd.auth.gr/",
                    tech: "ReactJS/Flask",
                    category: "website" 
                },
                {
                    name: "Meimaris eShop",
                    description: "Ecommerce setup + custom plugins",
                    image: "https://user-images.githubusercontent.com/29873078/192573951-b498e889-bd94-4341-8254-50bb96b293bc.png",
                    link: "https://www.meimaris.com",
                    tech: "CS-Cart/PHP",
                    category: "website" 
                },
                {
                    name: "Alien Logger",
                    description: "MaaS (Malware as a Service) website offering an easier to use alternative from the traditional keylogger.",
                    image: "https://user-images.githubusercontent.com/29873078/113494787-5b528d80-94f4-11eb-90af-5170fa9b8ff2.png",
                    link: "https://github.com/TasosY2K/Alien-Logger",
                    tech: "NodeJS/Express.js/Python",
                    category: "website" 
                },
                {
                    name: "Lit Blog",
                    description: "A minimal portfolio/blog CMS that can be set up in a breeze.",
                    image: "https://camo.githubusercontent.com/240e94d1a14f3f4142f7903cb1a4c609614e89790df9f0265b3bfcbd8056ffac/68747470733a2f2f696d616765732d6578742d312e646973636f72646170702e6e65742f65787465726e616c2f457448354c5042355f67703331426933795a4a616254625a644d39567a6d795f75582d536c6f6d665a57342f68747470732f692e696d6775722e636f6d2f463454677a35362e706e673f77696474683d393334266865696768743d343733",
                    link: "https://github.com/TasosY2K/lit-blog",
                    tech: "NodeJS/Express.js/Webpack",
                    category: "website" 
                },
                {
                    name: "Anon Image",
                    description: "Web app for uploading anonymous password protected and easily shareable images.",
                    image: "https://user-images.githubusercontent.com/29873078/97197071-e09f7c80-17b5-11eb-9c01-b775353f8149.png",
                    link: "https://github.com/TasosY2K/anon-image",
                    tech: "NodeJS/Express.js/Webpack",
                    category: "website" 
                },
                {
                    name: "Light Scraper",
                    description: "An optical character recognition search tool for screenshots from prnt.sc.",
                    image: "https://user-images.githubusercontent.com/29873078/73987010-c122a400-4947-11ea-928c-077ef7f8acad.png",
                    link: "https://github.com/TasosY2K/light-scraper",
                    tech: "NodeJS",
                    category: "software" 
                },
                {
                    name: "Espresso Bot",
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
                    name: "Lean Tracker",
                    description: "A fast and easy to use ip logger built on express.js.",
                    image: "https://user-images.githubusercontent.com/29873078/192578433-7ad8b819-fd95-4703-836e-3b6564455436.jpg",
                    link: "https://github.com/TasosY2K/lean-tracker",
                    tech: "NodeJS/Express.js",
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
                    image: "https://user-images.githubusercontent.com/29873078/192579779-161aac10-27e4-4406-a1c8-45d210b298be.png",
                    link: "https://tasosy2k.github.io/Random-IP-Generator",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "King Crypter Demo Site",
                    description: "Landing page for the upcoming King Crypter project.",
                    image: "https://user-images.githubusercontent.com/29873078/192584117-a3dfc76f-750b-40a3-9c14-97d1a8fd5796.png",
                    link: "https://kingcrypter.netlify.app/",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "Digitalza Sec Site",
                    description: "Landing page for my friends at Digitalza Sec.",
                    image: "https://user-images.githubusercontent.com/29873078/192584604-28127e63-beff-4d3b-9e6a-310e19033db2.png",
                    link: "https://digitalza.netlify.app",
                    tech: "HTML/CSS/JS",
                    category: "website"
                },
                {
                    name: "RedBull Basement Vote Bot",
                    description: "A bot for generating fake votes for https://basement.redbull.com/.",
                    image: "https://user-images.githubusercontent.com/29873078/192584932-412d5504-3685-4aeb-9d6f-1fcc4f4a3b1a.png",
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
