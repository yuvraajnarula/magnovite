<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import Card from "../../component/Card.svelte";
    let events = [{
        "title": "event1",
        "desc" : "lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. ",
        "link" : "/event/event1",
    },{
        "title": "event2",
        "desc" : "lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. ",
        "link" : "/event/event2",
    },{
        "title": "event3",
        "desc" : "lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. ",
        "link" : "/event/event3",
    },{
        "title": "event4",
        "desc" : "lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. ",
        "link" : "/event/event4",
    }]
</script>
<div class="about-div">
    <div class="bg-bubble"></div>
    <Nav />
    <div class="about-info">
        <h1>
            Our Events
        </h1>
        <p>
            lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. lorem ipsum is a sample text for content display to show the content distribution for mockups in UI design. 
        </p>
        <div class="about-grid">
            {#each events as event}
                <Card title={event.title} description={event.desc} link={event.link}  />
            {/each}
        </div>
    </div>
</div>