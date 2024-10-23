<script>
    import { page } from '$app/stores'; // to access the route parameter
    import "../../../public/main.css";
    import Nav from "../../../component/Nav.svelte";
    import Card from "../../../component/Card.svelte";

    // Access the event ID from the URL
    let eventId;
    $: eventId = $page.params.id; // dynamically update based on URL

    // Dummy event data (you can fetch actual data using fetch API or load functions)
    let eventTitle = `Event ${eventId}`;
    let eventDescription = `This is the description of event ${eventId}. More details to be added here.`;
    let eventLink = "#";
</script>

<Nav />  <!-- Navigation Bar Component -->

<div class="event-div">
    <div class="bg-bubble"></div>
    <div class="event-info">
        <h1>
            {eventTitle}
        </h1>
        <p>
            {eventDescription}
        </p>
    </div>
</div>