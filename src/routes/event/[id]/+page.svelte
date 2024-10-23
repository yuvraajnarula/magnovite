<script>
    import { page } from '$app/stores';
    import "../../../public/main.css";
    import Nav from "../../../component/Nav.svelte";
    import Card from "../../../component/Card.svelte";
    let eventId;
    $: eventId = $page.params.id; 
</script>

<Nav />

<div class="event-div">
    <div class="bg-bubble"></div>
    <div class="event-info">
        <h1>
            {eventId}
        </h1>
        <p>
            This is a test event
        </p>
    </div>
</div>