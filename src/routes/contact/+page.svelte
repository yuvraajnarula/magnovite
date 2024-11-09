<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
  import MobileNav from "../../component/MobileNav.svelte";
  import Footer from "../../component/Footer.svelte";
  let contact = [
    {
        "name": "Anirudh Sharma",
    },
    {
        "name": "Tanmai Mukashi",
    },
    {
        "name": "Vyshnavi",
    },
    {
        "name" : "Meet Ravrani"
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
    </div>
</div>
<Footer />