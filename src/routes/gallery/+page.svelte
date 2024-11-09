<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import MobileNav from "../../component/MobileNav.svelte";
    import { onMount } from 'svelte';
  import Footer from "../../component/Footer.svelte";

    let bgList = [
        "/AT3A3005.JPG",
        "/AT3A3015.JPG", "/AT3A3017.JPG", "/AT3A3020.JPG", "/AT3A3022.JPG",
        "/AT3A3023.JPG", "/AT3A3025.JPG", "/AT3A3200.JPG", "/AT3A3207.JPG",
        "/DSC_0128.JPG", "/DSC_0166.JPG", "/DSC_0169.JPG", "/IMG_0173.JPG",
        "/IMG_0269.JPG", "/IMG_0676.JPG", "/IMG_0679.JPG", "/IMG_0767.JPG",
        "/IMG_0772.JPG", "/IMG_0777.JPG", "/IMG_0797.JPG", "/IMG_0824.JPG",
        "/IMG_0833.JPG", "/IMG_0850.JPG", "/IMG_0853.JPG", "/IMG_0864.JPG",
        "/IMG_1090.JPG", "/IMG_5467.JPG", "/IMG_5470.JPG", "/IMG_9700.JPG",
        "/IMG_9749.JPG", "/IMG_9824.JPG", "/IMG_9897.JPG", "/IMG_9922.JPG",
        "/IMG_9991.JPG", "/IMG_9999.JPG", "/IMG_9992.JPG",
    ];
    
    let currentIndex = 0;
    let galleryImages = [
        ".gal-1",
        ".gal-2",
        ".gal-3",
        ".gal-4",
        ".gal-5",
    ];

    function updateGallery() {
        galleryImages = [0, 1, 2, 3, 4].map(i => bgList[(currentIndex + i) % bgList.length]);
    }

    function galleryNext() {
        currentIndex = (currentIndex + 5) % bgList.length;
        updateGallery();
    }

    function galleryPrev() {
        currentIndex = (currentIndex - 5 + bgList.length) % bgList.length;
        updateGallery();
    }

    // Initialize the gallery when component is mounted
    onMount(updateGallery);
</script>

<div class="gallery-div">
    <div class="bg-bubble"></div>
    <Nav />
    <MobileNav />
    <center>
        <h1>Our Gallery</h1>
        <p>
            Checkout our memory hauls from last year and be a part of it.
        </p>
        <div class="gallery-flex">
            <div class="gallery-flex-1">
                <div class="gal-1" style="background-image: url({galleryImages[0]});"></div>
                <div class="gal-2" style="background-image: url({galleryImages[1]});"></div>
            </div>
            <div class="gallery-flex-2">
                <div class="gal-3" style="background-image: url({galleryImages[2]});"></div>
                <div class="gal-4" style="background-image: url({galleryImages[3]});"></div>
            </div>
            <div class="gallery-flex-3">
                <div class="gal-5" style="background-image: url({galleryImages[4]});"></div>
                <div class="gallery-controls">
                    <div class="gal-l" on:click={galleryPrev}>
                        <!-- SVG content for left arrow -->
                        <svg width="80" height="8" viewBox="0 0 80 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M0.646447 3.64645C0.451184 3.84171 0.451184 4.15829 0.646447 4.35355L3.82843 7.53553C4.02369 7.7308 4.34027 7.7308 4.53553 7.53553C4.7308 7.34027 4.7308 7.02369 4.53553 6.82843L1.70711 4L4.53553 1.17157C4.7308 0.976311 4.7308 0.659728 4.53553 0.464466C4.34027 0.269204 4.02369 0.269204 3.82843 0.464466L0.646447 3.64645ZM79.5 4.5C79.7761 4.5 80 4.27614 80 4C80 3.72386 79.7761 3.5 79.5 3.5V4.5ZM1 4.5H79.5V3.5H1V4.5Z" fill="url(#paint0_linear_39_151)"/>
                            <defs>
                            <linearGradient id="paint0_linear_39_151" x1="1" y1="4.5" x2="79.5" y2="4.5" gradientUnits="userSpaceOnUse">
                            <stop stop-color="#56A48F"/>
                            <stop offset="1" stop-color="#4FFFE5"/>
                            </linearGradient>
                            </defs>
                        </svg>                  
                    </div>
                    <div class="gal-r" on:click={galleryNext}>
                        <!-- SVG content for right arrow -->
                        <svg width="80" height="8" viewBox="0 0 80 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M1 3.5C0.723858 3.5 0.5 3.72386 0.5 4C0.5 4.27614 0.723858 4.5 1 4.5V3.5ZM79.8536 4.35355C80.0488 4.15829 80.0488 3.84171 79.8536 3.64645L76.6716 0.464466C76.4763 0.269204 76.1597 0.269204 75.9645 0.464466C75.7692 0.659728 75.7692 0.976311 75.9645 1.17157L78.7929 4L75.9645 6.82843C75.7692 7.02369 75.7692 7.34027 75.9645 7.53553C76.1597 7.7308 76.4763 7.7308 76.6716 7.53553L79.8536 4.35355ZM1 4.5H79.5V3.5H1V4.5Z" fill="url(#paint0_linear_39_148)"/>
                            <defs>
                            <linearGradient id="paint0_linear_39_148" x1="1" y1="4.5" x2="79.5" y2="4.5" gradientUnits="userSpaceOnUse">
                            <stop stop-color="#56A48F"/>
                            <stop offset="1" stop-color="#4FFFE5"/>
                            </linearGradient>
                            </defs>
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </center> 
</div>

<style>
    /* Add your CSS styling here */
    .gal-1,.gal-2,.gal-3,.gal-4,.gal-5{
        transition: background-image 0.5s ease;
    }
    .gal-l,.gal-r{
        cursor: pointer;
    }
</style>
<Footer />