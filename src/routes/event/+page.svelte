<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
    import MobileNav from "../../component/MobileNav.svelte";
    let events = [{
        "title": "Technical Events",
        "desc" : "Dive into the latest tech trends and advancements with hands-on experiences.",
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeN7wq_nVIGBPyjSbk8m_9mFr0O0gwJJelPEUsPNugg-e_LdA/viewform",
    },{
        "title": "Management Events",
        "desc" : "Explore insights into the world of business, networking, and innovation.",
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLScJzDO0MyrJQVtvmCkiVpC_OfH1da4TCWQiCck2Z1UYyqfYGQ/viewform",
    },{
        "title": "Psychology Events",
        "desc" : "Gain understanding and insights into human behavior and mental wellness.",
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSci6pUM6ma06tt3Jtf3OtZw_XFIth8vypqi6-XtjjUDPKZSgw/viewform",
    },{
        "title": "Cultural Events",
        "desc" : "Celebrate diversity through art, music, and traditions from around the world.",
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSd89HjabndqYQd7GBVYeSbia3lVjZg-pUbfS7Xg9Fvyx9yQsA/viewform",
    },{
        "title": "Debate Events",
        "desc" : "Engage in thought-provoking debates and sharpen your persuasive skills.",
        "link" : "https://docs.google.com/forms/d/1fmqfJHTdScI2an-g7dyijg52qrZfhoYzox6rkJFEio0/viewform",
    },{
        "title": "Design Events",
        "desc" : "Unleash creativity with workshops and challenges in various design fields.",
        "link" : "https://docs.google.com/forms/d/e/1FAIpQLSeFH1mzF_tG5UojbuC-zJePwThP-PT33a1ysaRjbfHhB9SZjA/viewform",
    }]
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
        <div class="about-grid">
            {#each events as event}
                <Card title={event.title} description={event.desc} link={event.link}  />
            {/each}
        </div>
    </div>
</div>