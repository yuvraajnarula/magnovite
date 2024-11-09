<script>
    export let tags = [];
    export let activeTag = 'All'; 
    let scrollContainer;
    export let handleTagClick;
</script>

<div class="tags-flex">
    <ul class="tags-carousel" bind:this={scrollContainer}>
        <li>
            <button 
                class="tag-button {activeTag === 'All' ? 'active' : ''}" 
                on:click={() => handleTagClick('All')}
            >
                <span>All</span>
            </button>
        </li>
        {#each tags as tag}
            <li>
                <button 
                    class="tag-button {activeTag === tag ? 'active' : ''}" 
                    on:click={() => {
                        console.log("Clicked tag:", tag);
                        handleTagClick(tag);
                    }}
                >
                    <span>{tag[0].toUpperCase() + tag.slice(1)}</span>
                </button>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tags-flex {
        width: 100%;
        position: relative;
    }
    .tags-flex ul{
        display: flex;
        list-style: none;
        align-items: center;
        width: 100%;
        margin-left: -5.5vw;
        padding-left: 5vw;
        margin-right: 4vw;
        transition: all 0.5s ease;
        overflow-x: auto;
        scroll-behavior: smooth;
        -ms-overflow-style: none;  
        scrollbar-width: none; 
    }
    .tags-flex ul::-webkit-scrollbar {
        display: none;
    }
    .tags-flex ul li button {
    cursor: pointer;
    padding: 10px 20px;
    position: relative;
    border: none;
    margin: 10px 10px;
    letter-spacing: 1px;
    font-family: "Inter", sans-serif;
    font-size: 0.9vw;
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(5.6px);
    border: 2px solid rgba(255, 255, 255, 0.05);
    border-radius: 10px;
    transition: all 0.5s ease;
    white-space: nowrap;  
    display: inline-flex; 
    align-items: center;
    justify-content: center;
}
    .tags-flex ul li button:hover{
        transform: translateY(-5px);
    }
    .tags-flex ul li button.active {
        background: rgba(255, 255, 255, 0.2);
        border-color: rgba(255, 255, 255, 0.3);
    }
    .tags-flex ul li button.active span {
        color: #fff;
    }
    .tags-flex ul li button span{
        width: fit-content;
        color: rgba(255, 255, 255, 0.7);
    }
    @media only screen and (max-width: 768px){
        .tags-flex ul li button{
            font-size: 2.75vw;
            min-width: 25vw !important;
        }
    }
</style>