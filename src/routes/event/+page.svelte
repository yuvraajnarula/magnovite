<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
    import MobileNav from "../../component/MobileNav.svelte";
  import Footer from "../../component/Footer.svelte";
  import { onMount } from "svelte";
  import Carousel from "../../component/Carousel.svelte";
      // let events = [{
    //     "title": "Technical Events",
    //     "desc" : "Dive into the latest tech trends and advancements with hands-on experiences.",
    //     //https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform
    //     "link" : "/event/technical",
    // },{
    //     "title": "Management Events",
    //     "desc" : "Explore insights into the world of business, networking, and innovation.",
    //     //https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform
    //     "link" : "/event/management",
    // },{
    //     "title": "Psychology Events",
    //     "desc" : "Gain understanding and insights into human behavior and mental wellness.",
    //     //https://docs.google.com/forms/d/e/1FAIpQLSci6pUM6ma06tt3Jtf3OtZw_XFIth8vypqi6-XtjjUDPKZSgw/viewform
    //     "link" : "/event/psychology",
    // },{
    //     "title": "Cultural Events",
    //     "desc" : "Celebrate diversity through art, music, and traditions from around the world.",
    //     //https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform
    //     "link" : "/event/cultural",
    // },{
    //     "title": "Debate Events",
    //     "desc" : "Engage in thought-provoking debates and sharpen your persuasive skills.",
    //     //https://docs.google.com/forms/d/1fmqfJHTdScI2an-g7dyijg52qrZfhoYzox6rkJFEio0/viewform
    //     "link" : "/event/debate",
    // },{
    //     "title": "Design Events",
    //     "desc" : "Unleash creativity with workshops and challenges in various design fields.",
    //     //https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform
    //     "link" : "/event/design",
    // }]
    let events = [
    // Management Events
    {
        "title": "BEST MANAGEMENT TEAM",
        "desc": "Compete in corporate strategy and team dynamics for top management honors.",
        "tags": ["management", "strategy"]
    },
    {
        "title": "CORPORATE SOCIAL RESPONSIBILITY",
        "desc": "Explore the role of companies in making a positive societal impact.",
        "tags": ["management", "social impact"]
    },
    {
        "title": "BEST MANAGER",
        "desc": "Showcase leadership skills through challenges in a competitive environment.",
        "tags": ["management", "leadership"]
    },
    {
        "title": "FINANCE",
        "desc": "Navigate complex financial scenarios in a competitive team-based event.",
        "tags": ["management", "finance"]
    },
    {
        "title": "HUMAN RESOURCES",
        "desc": "Engage in exciting HR-based challenges, including case studies and hiring simulations.",
        "tags": ["management", "HR"]
    },
    {
        "title": "PUBLIC RELATIONS",
        "desc": "Develop communication strategies in a fast-paced PR competition.",
        "tags": ["management", "PR"]
    },
    {
        "title": "MARKETING",
        "desc": "Pitch and market products effectively to stand out in the competition.",
        "tags": ["management", "marketing"]
    },
    {
        "title": "BUSINESS QUIZ",
        "desc": "Test your business knowledge with a challenging quiz competition.",
        "tags": ["management", "quiz"]
    },
    {
        "title": "BUSINESS PLAN",
        "desc": "Create a detailed business plan, from idea inception to execution.",
        "tags": ["management", "planning"]
    },

    // Architecture Events
    {
        "title": "REVIVAL OUTLOOK",
        "desc": "Fashion design competition focused on innovative concepts.",
        "tags": ["architecture", "design"]
    },
    {
        "title": "SPILL ART",
        "desc": "Create art from a spilled ink pattern using unique techniques.",
        "tags": ["architecture", "art"]
    },
    {
        "title": "TERRABSTRACT",
        "desc": "Sculpt abstract designs using clay provided on-site.",
        "tags": ["architecture", "sculpture"]
    },
    {
        "title": "GLIMPSE INTO THE UNFOCUSED",
        "desc": "An online photography competition based on assigned themes.",
        "tags": ["architecture", "photography"]
    },

    // Technical Events
    {
        "title": "RC ROBOSOCCER 2.0",
        "desc": "Build and program robots to play soccer and compete with other teams.",
        "tags": ["technical", "robotics", "engineering"]
    },
    {
        "title": "MAZE – MERISE",
        "desc": "Design an autonomous robot to navigate a maze efficiently.",
        "tags": ["technical", "robotics", "programming"]
    },
    {
        "title": "ENIGMA REDESIGNED",
        "desc": "A cryptographic challenge with multiple rounds of code-breaking and debugging.",
        "tags": ["technical", "coding", "cryptography"]
    },
    {
        "title": "SPARK-A-THON",
        "desc": "Pitch innovative tech solutions through ideation and prototyping.",
        "tags": ["technical", "innovation", "pitching"]
    },
    {
        "title": "SMART PITCH",
        "desc": "Pitch civil engineering ideas with innovative business models.",
        "tags": ["technical", "pitching", "civil engineering"]
    },
    {
        "title": "INNOVATIVE CAD DESIGNER",
        "desc": "Showcase creativity and skill in computer-aided design.",
        "tags": ["technical", "design", "CAD"]
    },
    {
        "title": "THE GENTLEMAN BURGLAR",
        "desc": "Simulate a bank heist through rounds focused on decryption, debugging, and circuit design.",
        "tags": ["technical", "coding", "circuit design"]
    },
    {
        "title": "OHM-AZING BUILD-A-THON",
        "desc": "Timed circuit-building rounds to test electrical engineering skills.",
        "tags": ["technical", "circuit design", "engineering"]
    },
    {
        "title": "EV HACKATHON",
        "desc": "Engage in electric vehicle challenges, from part identification to real-time battery monitoring.",
        "tags": ["technical", "engineering", "sustainability"]
    },

    // Psychology Events
    {
        "title": "HOW I MET YOUR KILLER",
        "desc": "Solve a fictional murder mystery through detective skills and teamwork.",
        "tags": ["psychology", "mystery", "teamwork"]
    },
    {
        "title": "AD-VENTURE",
        "desc": "Reimagine ordinary products and pitch creative marketing campaigns.",
        "tags": ["psychology", "creativity", "marketing"]
    },

    // Cultural Events
    {
        "title": "BATTLE OF BANDS",
        "desc": "Showcase your musical talent in an energetic battle of bands competition.",
        "tags": ["cultural", "music", "performance"]
    },
    {
        "title": "ACAPELLA AND GROUP SINGING",
        "desc": "Team singing event celebrating vocal harmony and creativity.",
        "tags": ["cultural", "music", "singing"]
    },
    {
        "title": "SOLO SINGING (WESTERN)",
        "desc": "Individual singing competition in the western music category.",
        "tags": ["cultural", "music", "solo"]
    },
    {
        "title": "SOLO SINGING (INDIAN)",
        "desc": "Showcase talent in Indian music with solo singing performances.",
        "tags": ["cultural", "music", "Indian"]
    },
    {
        "title": "INDIAN GROUP DANCE",
        "desc": "A group dance competition celebrating Indian dance forms.",
        "tags": ["cultural", "dance", "Indian"]
    },
    {
        "title": "WESTERN GROUP DANCE",
        "desc": "Group dance competition focusing on Western dance styles.",
        "tags": ["cultural", "dance", "Western"]
    },
    {
        "title": "SPOT CHOREOGRAPHY",
        "desc": "A fast-paced choreography competition with on-the-spot themes.",
        "tags": ["cultural", "dance", "choreography"]
    },
    {
        "title": "STREET PLAY",
        "desc": "Perform compelling street theater with social or comedic themes.",
        "tags": ["cultural", "theater", "social"]
    },
    {
        "title": "INK AND TALE",
        "desc": "Create a captivating short story or comic based on assigned characters and genres.",
        "tags": ["cultural", "creativity", "storytelling"]
    }
];
// Create a Set to store unique tags
let uniqueTags = new Set();
events.forEach(event => {
    event.tags.forEach(tag => {
        uniqueTags.add(tag);
    });
});
const tags = Array.from(uniqueTags);
onMount(()=>{
    let search = document.querySelector(".search");
    search.addEventListener("keyup",()=>{
        let query = search.value.toLowerCase();
        let cards = document.querySelectorAll(".card-component");
        cards.forEach(card=>{
            let title = card.querySelector(".card-title").textContent.toLowerCase();
            let tags = card.querySelector(".s").value;
            if (title.includes(query) || tags.includes(query)){
                card.style.display = "block";
            }else{
                card.style.display = "none";
            }
        })
    })
});
</script>
<div class="about-div">
    <div class="bg-bubble"></div>
    <Nav />
    <MobileNav />
    <div class="about-info">
        <h1>
            Our Events
        </h1>
        <p>
            Welcome! Register now to secure your spot at our upcoming events. Don't miss out on unique experiences designed for learning, enjoyment, and connection. Select your event below and register today!            
        </p>
        <a href="/doc/brochure.pdf" target="_blank">
            <span>
                View Brochure
            </span>
        </a>
        <!-- <div class="tags-flex">
            <ul class="tags-carousel">
                    <li>
                        <button>
                            <span>
                                All
                            </span>
                        </button>
                    </li>
                    {#each tags as tag}
                    <li>
                        <button>
                            <span>
                                {tag[0].toUpperCase() + tag.slice(1)}
                            </span>
                        </button>
                    </li>
                    {/each}
                </ul>
        </div> --><br><br>
        <input type="search" placeholder="Search Events" class="search"/>
        <Carousel tags={tags} />
        <div class="about-grid">
            {#each events as event}
                <Card title={event.title} description={event.desc} tag={event.tags}/>
            {/each}
        </div>
    </div>
</div>
<Footer />
<style>
    .search{
        background: rgba(255, 255, 255, 0.05);
        padding: 15px;
        border: 2px solid rgba(255, 255, 255, 0.05);
        cursor: pointer;
        transition: all 0.4s ease;
        font-family: "Inter", sans-serif;
        color: #eee;
        width: 20vw;
        border-radius: 10px;
        cursor: auto;
    }
    .search::placeholder{
        color: rgba(255, 255, 255, 0.05);
    }
    .search:focus{
        outline: none;
    }
    @media only screen and (max-width:768px){
        .search{
            width: 80%;
        }
    }
</style>