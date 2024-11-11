<script>
    import { onMount } from 'svelte';

    let isOpen = false;

    function openNav() {
        isOpen = true;
    }

    function closeNav() {
        isOpen = false;
    }
</script>
<div class="mobile-nav-flex">
    <div class="mobile-logo">
        </div>
        <div class="hamburger" on:click={openNav}>☰</div>
</div>
<div class="mobile-nav-component {isOpen ? 'open' : ''}" id="myNav">
    <span class="closebtn" on:click={closeNav}>&times;</span>
    <div class="hamburger-menu">
        <ul class="burger-list">
            <li>
                <img src="/magnovite.png" width="100" height="100" alt="">
            </li>
            <li><a href="/">Home</a></li>
            <li><a href="/event">Event</a></li>
            <li><a href="/gallery">Gallery</a></li>
            <li><a href="/contact">Contact</a></li>
            <li><a href="https://linktr.ee/magnovite24christkengeri" target="_blank">Register</a></li>
        </ul>
    </div>
</div>
