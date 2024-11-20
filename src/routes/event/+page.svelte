<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
    import MobileNav from "../../component/MobileNav.svelte";
    import Footer from "../../component/Footer.svelte";
    import { onMount } from "svelte";
    import Carousel from "../../component/Carousel.svelte";
    //     "title": "Debate Events",
    //     "desc" : "Engage in thought-provoking debates and sharpen your persuasive skills.",
    //     //https://docs.google.com/forms/d/1fmqfJHTdScI2an-g7dyijg52qrZfhoYzox6rkJFEio0/viewform
    //     "link" : "/event/debate",
    let events = [
    // Management Events
    {
        "title": "BEST MANAGEMENT TEAM",
        "desc": "Compete in corporate strategy and team dynamics for top management honors.",
        "tags": ["management", "strategy"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img": "/eventcards/bestmanagement.jpg"
    },
    {
        "title": "CORPORATE SOCIAL RESPONSIBILITY",
        "desc": "Explore the role of companies in making a positive societal impact.",
        "tags": ["management", "social impact"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/corporatesocial.jpg"
   
    },
    {
        "title": "BEST MANAGER",
        "desc": "Showcase leadership skills through challenges in a competitive environment.",
        "tags": ["management", "leadership"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/bestmanager.jpg"
    },
    {
        "title": "FINANCE",
        "desc": "Navigate complex financial scenarios in a competitive team-based event.",
        "tags": ["management", "finance"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/finance.jpg"
    },
    {
        "title": "HUMAN RESOURCES",
        "desc": "Engage in exciting HR-based challenges, including case studies and hiring simulations.",
        "tags": ["management", "HR"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/hr.jpg"
    },
    {
        "title": "PUBLIC RELATIONS",
        "desc": "Develop communication strategies in a fast-paced PR competition.",
        "tags": ["management", "PR"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/pr.jpg"
    },
    {
        "title": "MARKETING",
        "desc": "Pitch and market products effectively to stand out in the competition.",
        "tags": ["management", "marketing"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/marketing.jpg"
    },
    {
        "title": "BUSINESS QUIZ",
        "desc": "Test your business knowledge with a challenging quiz competition.",
        "tags": ["management", "quiz"],
        "link": "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/businessquiz.jpg"
    },
    {
        "title": "BUSINESS PLAN",
        "desc": "Create a detailed business plan, from idea inception to execution.",
        "tags": ["management", "planning"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
        "img" : "/eventcards/businessplan.jpg"
    },

    // Architecture Events
    {
        "title": "REVIVAL OUTLOOK",
        "desc": "Fashion design competition focused on innovative concepts.",
        "tags": ["architecture", "design"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform",
        "img" : "/eventcards/revival.jpg"
    },
    {
        "title": "SPILL ART",
        "desc": "Create art from a spilled ink pattern using unique techniques.",
        "tags": ["architecture", "art"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform",
        "img" : "/eventcards/spillart.jpg"
    },
    {
        "title": "TERRABSTRACT",
        "desc": "Sculpt abstract designs using clay provided on-site.",
        "tags": ["architecture", "sculpture"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform",
        "img" : "/eventcards/terrabstract.jpg"
    },
    {
        "title": "GLIMPSE INTO THE UNFOCUSED",
        "desc": "An online photography competition based on assigned themes.",
        "tags": ["architecture", "photography"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform",
        "img" : "/eventcards/glimpse.jpg"
    },

    // Technical Events
    {
        "title": "RC ROBOSOCCER 2.0",
        "desc": "Build and program robots to play soccer and compete with other teams.",
        "tags": ["technical", "robotics", "engineering"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/robosoc.jpg"
    },
    {
        "title": "MAZE – MERISE",
        "desc": "Design an autonomous robot to navigate a maze efficiently.",
        "tags": ["technical", "robotics", "programming"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/maze.jpg"
    },
    {
        "title": "ENIGMA REDESIGNED",
        "desc": "A cryptographic challenge with multiple rounds of code-breaking and debugging.",
        "tags": ["technical", "coding", "cryptography"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/enigma.jpg"
    },
    {
        "title": "SPARK-A-THON",
        "desc": "Pitch innovative tech solutions through ideation and prototyping.",
        "tags": ["technical", "innovation", "pitching"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/spark.jpg"
    },
    {
        "title": "SMART PITCH",
        "desc": "Pitch civil engineering ideas with innovative business models.",
        "tags": ["technical", "pitching", "civil engineering"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/smartpitch.jpg"
    },
    {
        "title": "INNOVATIVE CAD DESIGNER",
        "desc": "Showcase creativity and skill in computer-aided design.",
        "tags": ["technical", "design", "CAD"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/cad.jpg"
    },
    {
        "title": "THE GENTLEMAN BURGLAR",
        "desc": "Simulate a bank heist through rounds focused on decryption, debugging, and circuit design.",
        "tags": ["technical", "coding", "circuit design"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/gentlemen.jpg"
    },
    {
        "title": "OHM-AZING BUILD-A-THON",
        "desc": "Timed circuit-building rounds to test electrical engineering skills.",
        "tags": ["technical", "circuit design", "engineering"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/ohmazing.jpg"
    },
    {
        "title": "EV HACKATHON",
        "desc": "Engage in electric vehicle challenges, from part identification to real-time battery monitoring.",
        "tags": ["technical", "engineering", "sustainability"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
        "img" : "/eventcards/evhackathon.jpg"
    },

    // Psychology Events
    {
        "title": "HOW I MET YOUR KILLER",
        "desc": "Solve a fictional murder mystery through detective skills and teamwork.",
        "tags": ["psychology", "mystery", "teamwork"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSci6pUM6ma06tt3Jtf3OtZw_XFIth8vypqi6-XtjjUDPKZSgw/viewform",
        "img" : "/eventcards/kill.jpg"
    },
    {
        "title": "AD-VENTURE",
        "desc": "Reimagine ordinary products and pitch creative marketing campaigns.",
        "tags": ["psychology", "creativity", "marketing"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSci6pUM6ma06tt3Jtf3OtZw_XFIth8vypqi6-XtjjUDPKZSgw/viewform",
        "img" : "/eventcards/adventure.jpg"
    },
    {
        "title" : "Switch and Scene",
        "desc" : " Pairs of performers dive into spontaneous improv, facing sudden role reversals and genre changes with just minutes to prepare. Watch as they adapt on the fly, switching from strict boss to nervous employee or shifting from romance to horror in unpredictable and entertaining ways!  ",
        "tags": ["psychology", "creativity", "theatre"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSci6pUM6ma06tt3Jtf3OtZw_XFIth8vypqi6-XtjjUDPKZSgw/viewform",
        "img" : "/eventcards/switch.jpg"
    },
    {
        "title": "INK AND TALE",
        "desc": "Create a captivating short story or comic based on assigned characters and genres.",
        "tags": ["psychology", "creativity", "storytelling"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/inktale.jpg"
    },
    //debate
    {
        "title": "Convince and Conquer : The Art of Persuasion",
        "desc" : 'A two-day event designed to challenge students to articulate and advocate for robust ideas on the theme of “Achieving Academic and Professional Balance for Industry Readiness.”'
        ,"tags" : ["debate","academia"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSdqz6Gyk9WOKXyShoXbT7xHjuLadrF_CsHN3X2ELwpNbYwTTA/viewform",
        "img" : "/eventcards/debate.jpg"
    },
    // Cultural Events
    {
        "title": "BATTLE OF BANDS",
        "desc": "Showcase your musical talent in an energetic battle of bands competition.",
        "tags": ["cultural", "music", "performance"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/bob.JPG"
    },
    {
        "title": "ACAPELLA AND GROUP SINGING",
        "desc": "Team singing event celebrating vocal harmony and creativity.",
        "tags": ["cultural", "music", "singing"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/acapella.jpg"
    },
    {
        "title": "SOLO SINGING (WESTERN)",
        "desc": "Individual singing competition in the western music category.",
        "tags": ["cultural", "music", "solo"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/westernsolo.png"
    },
    {
        "title": "SOLO SINGING (INDIAN)",
        "desc": "Showcase talent in Indian music with solo singing performances.",
        "tags": ["cultural", "music", "Indian"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
                "img" : "/eventcards/indiansolo.JPG"
    },
    {
        "title": "INDIAN GROUP DANCE",
        "desc": "A group dance competition celebrating Indian dance forms.",
        "tags": ["cultural", "dance", "Indian"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/indiangroup.jpg "
    },
    {
        "title": "WESTERN GROUP DANCE",
        "desc": "Group dance competition focusing on Western dance styles.",
        "tags": ["cultural", "dance", "Western"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/westerngroup.jpg"
    },
    {
        "title": "SPOT CHOREOGRAPHY",
        "desc": "A fast-paced choreography competition with on-the-spot themes.",
        "tags": ["cultural", "dance", "choreography"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/spotchoreo.JPG"
    },
    {
        "title": "STREET PLAY",
        "desc": "Perform compelling street theater with social or comedic themes.",
        "tags": ["cultural", "theater", "social"],
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
        "img" : "/eventcards/streetplay.jpg"
    },
];
// Create a Set to store unique tags
let uniqueTags = new Set();
events.forEach(event => {
    event.tags.forEach(tag => {
        uniqueTags.add(tag);
    });
});
const tags = Array.from(uniqueTags);
let activeTag = 'All';  // Add this line
    let searchQuery = '';   // Add this line
    let filteredEvents = events;

    function handleTagClick(selectedTag) {
        activeTag = selectedTag;
        filterEvents();
    }

    function filterEvents() {
        // First filter by tag
        let tagFiltered = activeTag === 'All' 
            ? events 
            : events.filter(event => event.tags.includes(activeTag));
        
        // Then filter by search query
        if (searchQuery) {
            const query = searchQuery.toLowerCase();
            filteredEvents = tagFiltered.filter(event => 
                event.title.toLowerCase().includes(query) || 
                event.tags.some(tag => tag.toLowerCase().includes(query))
            );
        } else {
            filteredEvents = tagFiltered;
        }
    }

    onMount(() => {
        let search = document.querySelector(".search");
        search.addEventListener("keyup", (e) => {
            searchQuery = e.target.value;
            filterEvents();
        });
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
        <input type="search" placeholder="Search Events" class="search" bind:value={searchQuery}/>
        <Carousel {tags} {activeTag} {handleTagClick} />
        <div class="about-grid">
            {#each filteredEvents as event}
                <Card title={event.title} description={event.desc} img={event.img} tag={event.tags} link={event.link}/>
            {/each}
        </div>
    </div>
    <Footer />
</div>
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
        background: rgba(255, 255, 255, 0.08);
        border:2px solid rgba(255, 255, 255, 0.08);
    }
    .active{
        background: rgba(255, 255, 255, 0.5);
    }
    .active span{
        color: #111 !important;
    }
    @media only screen and (max-width:768px){
        .search{
            width: 80%;
        }
    }
</style>