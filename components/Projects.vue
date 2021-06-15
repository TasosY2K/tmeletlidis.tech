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
                    tech: "NodeJS",
                    category: "software" 
                },
                {
                    name: "LeanTracker",
                    description: "A fast and easy to use ip logger built on express.js.",
                    image: "https://camo.githubusercontent.com/380aee9fcdc46d6f9f5a55279590e77787255df404fc71102b28588bd55455d2/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3630393835343237313831303330363034392f3638383338333036333030343238323930352f53637265656e73686f745f312e706e67",
                    link: "https://lean-tracker-demo.herokuapp.com/",
                    tech: "NodeJS/Express.js",
                    category: "website" 
                }
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