<script>
    import "../../public/main.css";
    import Nav from "../../component/Nav.svelte";
    import MobileNav from "../../component/MobileNav.svelte";
    import Footer from "../../component/Footer.svelte";
    let bgList = [
        "/DSC_0128.JPG", "/DSC_0166.JPG", "/DSC_0169.JPG", "/IMG_0173.JPG",
        "/DSC_0166.JPG", "/IMG_0676.JPG", "/IMG_0679.JPG", "/IMG_0767.JPG",
        "/IMG_0772.JPG", "/IMG_0777.JPG", "/IMG_0797.JPG", "/IMG_0824.JPG",
        "/IMG_0833.JPG", "/IMG_0850.JPG", "/IMG_0853.JPG", "/IMG_0864.JPG",
        "/IMG_1090.JPG", "/IMG_5467.JPG", "/IMG_5470.JPG", "/IMG_9700.JPG",
        "/IMG_9749.JPG", "/IMG_9824.JPG", "/IMG_9897.JPG", "/IMG_9922.JPG",
        "/IMG_9991.JPG", "/IMG_9999.JPG", "/IMG_9992.JPG",
        "/AT3A3015.JPG", 
        "/AT3A3005.JPG",    
    ];
    let selectedImage = null;

    function openLightbox(image) {
        selectedImage = image;
    }

    function closeLightbox() {
        selectedImage = null;
    }
</script>

<style>
    .gallery-div {
        padding: 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .gallery-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 16px;
        margin-top: 20px;
    }

    .gallery-grid img {
        width: 100%;
        height: 12.5vw;
        border-radius: 8px;
        cursor: pointer;
        transition: transform 0.2s;
    }

    .gallery-grid img:hover {
        transform: scale(1.05);
    }

    .lightbox {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.8);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    .lightbox img {
        max-width: 90%;
        max-height: 90%;
        border-radius: 8px;
    }

    .lightbox .close {
        position: absolute;
        top: 20px;
        right: 20px;
        font-size: 2rem;
        color: white;
        cursor: pointer;
    }
    @media only screen and (max-width:768px){
        
    .gallery-grid img {
        height: auto;        
    }
    }
</style>

<div class="gallery-div">
    <Nav />
    <MobileNav />
    <center>
        <h1>Our Gallery</h1>
        <p>Checkout our memory hauls from last year and be a part of it.</p>
    </center>
    
    <!-- Gallery Grid -->
    <div class="gallery-grid">
        {#each bgList as bg}
            <img src={bg} alt="Gallery Image" loading="lazy" on:click={() => openLightbox(bg)} />
        {/each}
    </div>

    <!-- Lightbox -->
    {#if selectedImage}
        <div class="lightbox" on:click={closeLightbox}>
            <span class="close" on:click|stopPropagation={closeLightbox}>&times;</span>
            <img src={selectedImage} alt="Selected Image" />
        </div>
    {/if}

    <Footer />
</div>
