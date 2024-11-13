<script>
import AOS from "aos";
import "aos/dist/aos.css";
import "../public/main.css";
import Nav from "../component/Nav.svelte";
import MobileNav from "../component/MobileNav.svelte";
import Footer from "../component/Footer.svelte";
import Loader from "../component/Loader.svelte";
import { onMount } from "svelte";

let isLoading = true;

onMount(() => {
    setTimeout(() => {
        isLoading = false;
    }, 3000);
});

//AOS init checker
onMount(()=>{
    if (AOS) {
        AOS.init();
    } else {
        console.error("AOS is not defined.");
    }
});

</script>

{#if isLoading}
    <Loader />
{:else}
    <div class="home-div">
        <div class="bg-bubble">
        </div>
        <Nav />
        <MobileNav />
        <div class="morph-div">
            <h1>
                MAGNOVITE'24
            </h1>
            <img src="./uni.png" alt="">
        </div>
        <div class="video-div" data-aos="fade-down">
            <h1> 
                Checkout<span>
                    Teaser
                </span>
            </h1>
            <center>
                <video src="./video.mp4" controls loop autoplay></video>
            </center>
        </div>
        <div style:height="10vh"></div>
                <div class="home-info" data-aos="fade-up">
                <ul>
                    <li>
                        <svg width="20" height="16" viewBox="0 0 20 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M10.0001 6.66667C9.11603 6.66667 8.26818 6.31548 7.64306 5.69036C7.01794 5.06523 6.66675 4.21739 6.66675 3.33333C6.66675 2.44928 7.01794 1.60143 7.64306 0.976311C8.26818 0.351189 9.11603 0 10.0001 0C10.8841 0 11.732 0.351189 12.3571 0.976311C12.9822 1.60143 13.3334 2.44928 13.3334 3.33333C13.3334 4.21739 12.9822 5.06523 12.3571 5.69036C11.732 6.31548 10.8841 6.66667 10.0001 6.66667ZM10.0001 1.33333C8.89341 1.33333 8.00008 2.22667 8.00008 3.33333C8.00008 4.44 8.89341 5.33333 10.0001 5.33333C11.1067 5.33333 12.0001 4.44 12.0001 3.33333C12.0001 2.22667 11.1067 1.33333 10.0001 1.33333Z" fill="white"/>
                            <path d="M18 12C17.6267 12 17.3333 11.7067 17.3333 11.3333C17.3333 10.96 17.6267 10.6667 18 10.6667C18.3733 10.6667 18.6667 10.3733 18.6667 10C18.6667 9.11595 18.3155 8.2681 17.6904 7.64298C17.0652 7.01786 16.2174 6.66667 15.3333 6.66667H14C13.6267 6.66667 13.3333 6.37333 13.3333 6C13.3333 5.62667 13.6267 5.33333 14 5.33333C15.1067 5.33333 16 4.44 16 3.33333C16 2.22667 15.1067 1.33333 14 1.33333C13.6267 1.33333 13.3333 1.04 13.3333 0.666667C13.3333 0.293333 13.6267 0 14 0C14.8841 0 15.7319 0.351189 16.357 0.976311C16.9821 1.60143 17.3333 2.44928 17.3333 3.33333C17.3333 4.16 17.04 4.90667 16.5333 5.49333C18.52 6.02667 20 7.84 20 10C20 11.1067 19.1067 12 18 12ZM2 12C0.893333 12 0 11.1067 0 10C0 7.84 1.46667 6.02667 3.46667 5.49333C2.97333 4.90667 2.66667 4.16 2.66667 3.33333C2.66667 2.44928 3.01786 1.60143 3.64298 0.976311C4.2681 0.351189 5.11595 0 6 0C6.37333 0 6.66667 0.293333 6.66667 0.666667C6.66667 1.04 6.37333 1.33333 6 1.33333C4.89333 1.33333 4 2.22667 4 3.33333C4 4.44 4.89333 5.33333 6 5.33333C6.37333 5.33333 6.66667 5.62667 6.66667 6C6.66667 6.37333 6.37333 6.66667 6 6.66667H4.66667C3.78261 6.66667 2.93477 7.01786 2.30964 7.64298C1.68452 8.2681 1.33333 9.11595 1.33333 10C1.33333 10.3733 1.62667 10.6667 2 10.6667C2.37333 10.6667 2.66667 10.96 2.66667 11.3333C2.66667 11.7067 2.37333 12 2 12ZM14 16H6C4.89333 16 4 15.1067 4 14V12.6667C4 10.0933 6.09333 8 8.66667 8H11.3333C13.9067 8 16 10.0933 16 12.6667V14C16 15.1067 15.1067 16 14 16ZM8.66667 9.33333C7.78261 9.33333 6.93477 9.68452 6.30964 10.3096C5.68452 10.9348 5.33333 11.7826 5.33333 12.6667V14C5.33333 14.3733 5.62667 14.6667 6 14.6667H14C14.3733 14.6667 14.6667 14.3733 14.6667 14V12.6667C14.6667 11.7826 14.3155 10.9348 13.6904 10.3096C13.0652 9.68452 12.2174 9.33333 11.3333 9.33333H8.66667Z" fill="white"/>
                            </svg>
                        <span>
                            7,000
                        </span>   
                    </li>
                    <li>
                        <svg width="20" height="20" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M17 3H5C2.79086 3 1 4.79086 1 7V17C1 19.2091 2.79086 21 5 21H17C19.2091 21 21 19.2091 21 17V7C21 4.79086 19.2091 3 17 3Z" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            <path d="M7 1V5M15 1V5M1 9H21" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                            
                        <span>
                            6th December - 7th December
                        </span>
                    </li>
                    <li>
                        <svg width="20" height="25" viewBox="0 0 18 23" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M9 2.001C7.14348 2.001 5.36301 2.7385 4.05025 4.05125C2.7375 5.36401 2 7.14448 2 9.001C2 11.863 3.782 14.624 5.738 16.763C6.73814 17.8526 7.82943 18.8549 9 19.759C9.17467 19.625 9.37967 19.4617 9.615 19.269C10.5548 18.4973 11.4393 17.6605 12.262 16.765C14.218 14.624 16 11.864 16 9.001C16 7.14448 15.2625 5.36401 13.9497 4.05125C12.637 2.7385 10.8565 2.001 9 2.001ZM9 22.215L8.433 21.825L8.43 21.823L8.424 21.818L8.404 21.804L8.329 21.751L8.059 21.554C6.69086 20.5258 5.41988 19.3743 4.262 18.114C2.218 15.876 0 12.637 0 9C3.55683e-08 6.61305 0.948211 4.32387 2.63604 2.63604C4.32387 0.948212 6.61305 0 9 0C11.3869 0 13.6761 0.948212 15.364 2.63604C17.0518 4.32387 18 6.61305 18 9C18 12.637 15.782 15.877 13.738 18.112C12.5804 19.3723 11.3098 20.5237 9.942 21.552C9.82805 21.6371 9.71305 21.7208 9.597 21.803L9.576 21.817L9.57 21.822L9.568 21.823L9 22.215ZM9 7.001C8.46957 7.001 7.96086 7.21171 7.58579 7.58679C7.21071 7.96186 7 8.47057 7 9.001C7 9.53143 7.21071 10.0401 7.58579 10.4152C7.96086 10.7903 8.46957 11.001 9 11.001C9.53043 11.001 10.0391 10.7903 10.4142 10.4152C10.7893 10.0401 11 9.53143 11 9.001C11 8.47057 10.7893 7.96186 10.4142 7.58679C10.0391 7.21171 9.53043 7.001 9 7.001ZM5 9.001C5 7.94013 5.42143 6.92272 6.17157 6.17257C6.92172 5.42243 7.93913 5.001 9 5.001C10.0609 5.001 11.0783 5.42243 11.8284 6.17257C12.5786 6.92272 13 7.94013 13 9.001C13 10.0619 12.5786 11.0793 11.8284 11.8294C11.0783 12.5796 10.0609 13.001 9 13.001C7.93913 13.001 6.92172 12.5796 6.17157 11.8294C5.42143 11.0793 5 10.0619 5 9.001Z" fill="white"/>
                        </svg>
                            
                        <span>
                            Christ University, Kengeri Campus, Bangalore
                        </span>
                    </li>
                </ul>
                <h1>
                    Welcome to<br>
                    Magnovite'24
                </h1>
                <p>
                    MAGNOVITE is the annual flagship fest organised by CHRIST (Deemed To be University), Kengeri Campus. It is an enigmatic nexus of creativity and collaboration, bringing healthy competition and positive connections between participants. It returns this year with its 14th edition, bringing back its unfading charm.
                </p>
            </div> 
        <div class="social-div">
            <ul>
                <li>
                    <a href="https://www.linkedin.com/company/christ-university-faculty-of-engineering/?originalSubdomain=in" target="_blank">
                        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M17.7778 0C18.3671 0 18.9324 0.234126 19.3491 0.650874C19.7659 1.06762 20 1.63285 20 2.22222V17.7778C20 18.3671 19.7659 18.9324 19.3491 19.3491C18.9324 19.7659 18.3671 20 17.7778 20H2.22222C1.63285 20 1.06762 19.7659 0.650874 19.3491C0.234126 18.9324 0 18.3671 0 17.7778V2.22222C0 1.63285 0.234126 1.06762 0.650874 0.650874C1.06762 0.234126 1.63285 0 2.22222 0H17.7778ZM17.2222 17.2222V11.3333C17.2222 10.3727 16.8406 9.45133 16.1613 8.77204C15.482 8.09274 14.5607 7.71111 13.6 7.71111C12.6556 7.71111 11.5556 8.28889 11.0222 9.15556V7.92222H7.92222V17.2222H11.0222V11.7444C11.0222 10.8889 11.7111 10.1889 12.5667 10.1889C12.9792 10.1889 13.3749 10.3528 13.6666 10.6445C13.9583 10.9362 14.1222 11.3319 14.1222 11.7444V17.2222H17.2222ZM4.31111 6.17778C4.80618 6.17778 5.28098 5.98111 5.63104 5.63104C5.98111 5.28098 6.17778 4.80618 6.17778 4.31111C6.17778 3.27778 5.34444 2.43333 4.31111 2.43333C3.81309 2.43333 3.33547 2.63117 2.98332 2.98332C2.63117 3.33547 2.43333 3.81309 2.43333 4.31111C2.43333 5.34444 3.27778 6.17778 4.31111 6.17778ZM5.85556 17.2222V7.92222H2.77778V17.2222H5.85556Z" fill="white"/>
                        </svg>    
                    </a>                    
                </li>
                <li class="line">
                </li>
                <li>
                    <a href="https://christuniversity.in" target="_blank">
                        <svg width="22" height="22" viewBox="0 0 22 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M21 11C21 13.6522 19.9464 16.1957 18.0711 18.0711C16.1957 19.9464 13.6522 21 11 21C8.34784 21 5.8043 19.9464 3.92893 18.0711C2.05357 16.1957 1 13.6522 1 11M21 11C21 8.34784 19.9464 5.8043 18.0711 3.92893C16.1957 2.05357 13.6522 1 11 1C8.34784 1 5.8043 2.05357 3.92893 3.92893C2.05357 5.8043 1 8.34784 1 11M21 11H1" stroke="white" stroke-linecap="round" stroke-linejoin="round"/>
                            <path d="M14.8461 11C14.6572 14.6569 13.3102 18.159 11 21C8.68969 18.159 7.34273 14.6569 7.15381 11C7.34273 7.34309 8.68969 3.841 11 1C13.3102 3.841 14.6572 7.34309 14.8461 11Z" stroke="white" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                            
                            
                    </a>    
                </li>
                <li class="line"></li>
                <li>
                    <a href="https://www.instagram.com/magnovite.kengeri/" target="_blank" rel="noopener noreferrer">
                        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M5.8 0H14.2C17.4 0 20 2.6 20 5.8V14.2C20 15.7383 19.3889 17.2135 18.3012 18.3012C17.2135 19.3889 15.7383 20 14.2 20H5.8C2.6 20 0 17.4 0 14.2V5.8C0 4.26174 0.61107 2.78649 1.69878 1.69878C2.78649 0.61107 4.26174 0 5.8 0ZM5.6 2C4.64522 2 3.72955 2.37928 3.05442 3.05442C2.37928 3.72955 2 4.64522 2 5.6V14.4C2 16.39 3.61 18 5.6 18H14.4C15.3548 18 16.2705 17.6207 16.9456 16.9456C17.6207 16.2705 18 15.3548 18 14.4V5.6C18 3.61 16.39 2 14.4 2H5.6ZM15.25 3.5C15.5815 3.5 15.8995 3.6317 16.1339 3.86612C16.3683 4.10054 16.5 4.41848 16.5 4.75C16.5 5.08152 16.3683 5.39946 16.1339 5.63388C15.8995 5.8683 15.5815 6 15.25 6C14.9185 6 14.6005 5.8683 14.3661 5.63388C14.1317 5.39946 14 5.08152 14 4.75C14 4.41848 14.1317 4.10054 14.3661 3.86612C14.6005 3.6317 14.9185 3.5 15.25 3.5ZM10 5C11.3261 5 12.5979 5.52678 13.5355 6.46447C14.4732 7.40215 15 8.67392 15 10C15 11.3261 14.4732 12.5979 13.5355 13.5355C12.5979 14.4732 11.3261 15 10 15C8.67392 15 7.40215 14.4732 6.46447 13.5355C5.52678 12.5979 5 11.3261 5 10C5 8.67392 5.52678 7.40215 6.46447 6.46447C7.40215 5.52678 8.67392 5 10 5ZM10 7C9.20435 7 8.44129 7.31607 7.87868 7.87868C7.31607 8.44129 7 9.20435 7 10C7 10.7956 7.31607 11.5587 7.87868 12.1213C8.44129 12.6839 9.20435 13 10 13C10.7956 13 11.5587 12.6839 12.1213 12.1213C12.6839 11.5587 13 10.7956 13 10C13 9.20435 12.6839 8.44129 12.1213 7.87868C11.5587 7.31607 10.7956 7 10 7Z" fill="white"/>
                            </svg>
                    </a>                    
                </li>
            </ul>
        </div>
        <div style:height="10vh"></div>
        <Footer />
        <div style:height=".5vh"></div>
</div>
{/if}
<style>
    @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');
    .morph-div{
        height: 100vh;
        width: 100%;
        overflow: hidden;
    }
    .morph-div h1{
        z-index: -1;
        font-size: 10.5vw;
        color: #eee;
        transition: all 1s ease-out;
        text-align: center;
        transform: translateY(-25%);
        animation-name: showText;
        font-weight: 600;
        animation-duration: 2s;
        /* animation-delay: 1s; */
        font-family: "Bebase Neue",sans-serif !important;
        animation-direction: forwards;
    }   
    .video-div{
        height: 100vh;
        width: 100%;
    }
    .video-div h1 {
        color: #eee;
        text-align: center;
        font-size: 3.5vw;
    }
    .video-div h1 span{
        background: linear-gradient(90deg, #56A48F 0%, #4FFFE5 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        text-fill-color: transparent;
    }
    .video-div video{
        width: 80%;-webkit-box-shadow: 3px 20px 41px 0px rgba(255,255,255,0.05);
-moz-box-shadow: 3px 20px 41px 0px rgba(255,255,255,0.05);
box-shadow: 3px 20px 41px 0px rgba(255,255,255,0.0.05);
        height: 95%;
        margin-top:  3.5vw;
    }
    @keyframes showText{
        from{
            opacity: 0;
            transform: translateY(-115%);
            filter: blur(30px);
        }
        to{
            opacity: 1;
            filter: blur(0);
            transform: translateY(-25%);
        }
    }
    .morph-div img {
        position: absolute;
        bottom: 0;
        width: 100%;
        height: 120vh;
        transition: opacity 1s ease;
        animation-name: showPosition;
        animation-duration: 2s;
        pointer-events: none;
        /* animation-delay: 0.75s; */
        animation-direction: forwards;
    }
    @keyframes showPosition{
        from { 
            transform: translateY(50vh);
            filter: blur(10px);
        }
        to{
            transform: translateY(0);
            filter: blur(0);
        }
    }
    @media only screen and (max-width: 768px){
        .morph-div h1{
            font-size: 12vw;
            font-weight: 900;
            margin-top: 45vw;
        }
        .morph-div img{
            height: 60vh;
            bottom: 40vw;
            transform: scale(1.75);
        }
        @keyframes showPosition{
        from { 
            transform: translateY(50vh) scale(1.75);
            filter: blur(10px);
        }
        to{
            transform: translateY(0) scale(1.75);
            filter: blur(0);
        }
    }
        .video-div h1{
            font-size: 5vw;
        }
        .video-div{
            height: fit-content;
        }
    }
</style>