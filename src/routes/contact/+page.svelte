<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
  import MobileNav from "../../component/MobileNav.svelte";
  import Footer from "../../component/Footer.svelte";
  let contact = [
    {
        "name" : "Jobin Shiji Daniel",
        "role" : "Faculty Incharge",
        "no" : 6282177450
    },  
  {
        "name": "Anirudh Sharma",
        "role" : "Core Member",
        "no" : 9315482466

    },
    {
        "name": "Tanmai Mukashi",
        "role" : "Core Member",
        "no" : 7019997296
    },
    {
        "name": "Vyshnavi",
        "role" : "Core Member",
        "no" : 8777366862
    },
    {
        "name" : "Meet Ravrani",
        "role" : "Core Member",
        "no" : 8105462515
    }
  ]
</script>
<div class="contact-div">
    <div class="bg-bubble"></div>
    <div class="bg-bubble-1"></div>
    <Nav />
    <MobileNav />
    <div class="contact-flex">
        <div class="contact-info">
            <h1>Contact us</h1>
            <p>
                <span>Address : </span> Dharmaram College Post, Hosur Road, Bengaluru - 560029,
                Karnataka, India
                <br>
                <span>Tel No : </span>+91 804012 9100 / 9600
                <br>
                <span>Email : </span> mail@christuniversity.in
                <br>
                <span>Web : </span> http://www.christuniversity.in                
            </p>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSc3QAe09f-B7hC1VS_tmR-UN0NNy9KwtSzeXTqLmQqi2ibjyQ/viewform" target="_blank">
                <span>
                    Check out for Accomodation details
                </span>
            </a>
        </div>
        <iframe title="Google Maps location of CHRIST University Kengeri Campus" src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15558.77568223423!2d77.4379779!3d12.8630352!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bae472f365fe219%3A0xcae219b3b46324db!2sCHRIST%20(Deemed%20to%20be%20University)%20Bangalore%20Kengeri%20Campus!5e0!3m2!1sen!2sin!4v1729685395465!5m2!1sen!2sin" width="451" height="193" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
    <div class="contact-grid">
        {#each contact as contact}
            <div class="contact-card">
                <h2>
                    {contact.name}
                </h2>
                <span>
                    SWO {contact.role}
                </span> <br><br>        
                <a href="tel:+{contact.no}">
                    <span>
                        Phone Number
                    </span>
                </a>
            </div>
        {/each}
    </div>
    <Footer />
</div>
<style>
    .contact-div{
        overflow: hidden !important;
        position: relative !important;
    }
    .contact-grid{
        display: flex;
        align-items: center;
        justify-content: space-around;
        padding: 10px;
        width: 92.5%;
        margin: 0 auto;
    }
    .contact-grid .contact-card{
        background-color: rgba(255,255,255,0.05);
        backdrop-filter: blur(4.8px);
        border: 2px solid rgba(255,255,255,0.05);
        border-radius: 10px;
        padding: 10px;
        height: 10vw;
        width: 15vw;
        text-align: center;
    }
    .contact-grid .contact-card h2{
        color: #eee;
    }
    .contact-grid .contact-card span{
        color: rgba(255,255,255,0.5);
    }
    .contact-grid .contact-card a {text-decoration: none;}
    .contact-grid .contact-card a span{
        background: linear-gradient(90deg, #56A48F 0%, #4FFFE5 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        text-fill-color: transparent;
    }
    @media only screen and (max-width:768px){
        .contact-grid{
            flex-direction: column;
        }
        .contact-card{
            width: 75vw !important;
            padding-bottom: 2.5vw;
            height: fit-content !important;
            margin-bottom: 10vw;
        }
    }
</style>