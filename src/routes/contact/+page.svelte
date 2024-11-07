<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
  import MobileNav from "../../component/MobileNav.svelte";
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
                lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. 
            </p>
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSc3QAe09f-B7hC1VS_tmR-UN0NNy9KwtSzeXTqLmQqi2ibjyQ/viewform" target="_blank">
                <span>
                    Check out for Accomodation details
                </span>
            </a>
        </div>
        <iframe title="Google Maps location of CHRIST University Kengeri Campus" src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15558.77568223423!2d77.4379779!3d12.8630352!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bae472f365fe219%3A0xcae219b3b46324db!2sCHRIST%20(Deemed%20to%20be%20University)%20Bangalore%20Kengeri%20Campus!5e0!3m2!1sen!2sin!4v1729685395465!5m2!1sen!2sin" width="451" height="193" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
    <div class="custom-select-wrapper">
        <select class="contact-dropdown">
            <option value="engineering">Engineering</option>
            <option value="business">Business and Management</option>
            <option value="arch">Architecture</option>
            <option value="psych">Psychology</option>
        </select>
        <span class="custom-arrow">
            <svg width="12" height="7" viewBox="0 0 12 7" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L6 6L11 1" stroke="url(#paint0_linear_39_177)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <defs>
                    <linearGradient id="paint0_linear_39_177" x1="11" y1="3.5" x2="1" y2="3.5" gradientUnits="userSpaceOnUse">
                        <stop stop-color="#56A48F"/>
                        <stop offset="1" stop-color="#4FFFE5"/>
                    </linearGradient>
                </defs>
            </svg>
        </span>
    </div>
    
    <div class="contact-grid">
    </div>
</div>