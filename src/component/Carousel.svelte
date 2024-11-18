<script>
    import { onMount } from "svelte";
    export let tags = [];
    export let activeTag = "All";
    export let handleTagClick = (tag) => {};

    let isOpen = false;
    let selectedDisplay = "Select Event";

    function toggleDropdown() {
        isOpen = !isOpen;
    }

    function selectTag(tag) {
        selectedDisplay = tag === "All" ? "Select Event" : tag[0].toUpperCase() + tag.slice(1);
        activeTag = tag;
        handleTagClick(tag);
        isOpen = false;
    }

    // Close dropdown when clicking outside
    function handleClickOutside(event) {
        const dropdown = event.target.closest('.select-container');
        if (!dropdown) {
            isOpen = false;
        }
    }

    // Add event listener when component is mounted
    onMount(() => {
        document.addEventListener('click', handleClickOutside);
        return () => {
            document.removeEventListener('click', handleClickOutside);
        };
    });
</script>

<div 
    class="select-container" 
    class:active={isOpen} 
    on:click|stopPropagation={toggleDropdown}
>
    <span class="selected-display" id="destination">{selectedDisplay}</span>
    <svg
        width="12"
        height="6"
        viewBox="0 0 12 6"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
    >
        <path
            d="M11.0689 0.156988L6.38395 4.76799C6.28173 4.86912 6.14374 4.92584 5.99995 4.92584C5.85616 4.92584 5.71817 4.86912 5.61595 4.76799L0.930947 0.157989C0.828092 0.0569129 0.689654 0.000276566 0.545447 0.000276566C0.401241 0.000276566 0.262803 0.0569129 0.159947 0.157989C0.109299 0.207366 0.0690468 0.266381 0.041563 0.331558C0.0140793 0.396735 -8.01086e-05 0.466754 -8.01086e-05 0.537489C-8.01086e-05 0.608223 0.0140793 0.678242 0.041563 0.743419C0.0690468 0.808595 0.109299 0.867611 0.159947 0.916988L4.84395 5.52699C5.15247 5.82991 5.56757 5.99963 5.99995 5.99963C6.43232 5.99963 6.84743 5.82991 7.15595 5.52699L11.8399 0.916988C11.8907 0.867596 11.9311 0.808518 11.9587 0.743249C11.9863 0.67798 12.0005 0.607843 12.0005 0.536988C12.0005 0.466133 11.9863 0.395998 11.9587 0.330729C11.9311 0.265459 11.8907 0.206381 11.8399 0.156988C11.7371 0.0559125 11.5987 -0.000723839 11.4544 -0.000723839C11.3102 -0.000723839 11.1718 0.0559125 11.0689 0.156988Z"
            fill="white"
        />
    </svg>

    <ul class="dropdown">
        <li on:click={() => selectTag("All")}>All</li>
        {#each tags as tag}
            <li on:click={() => selectTag(tag)}>
                {tag[0].toUpperCase() + tag.slice(1)}
            </li>
        {/each}
    </ul>
</div>
<style>
    .select-container{
        position: relative;
        display: inline-block;
        width: 17.5vw;
        padding: 15px;
        border-radius: 10px;
        background: rgba(255,255,255,0.06);
        text-align: left;
        color: #fff;
        cursor: pointer;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        margin-bottom: 20px;
        margin-left: .5vw;
        border:2px solid rgba(255,255,255,0.06);        
    }
    .select-container svg{
        float: right;
        margin-top: .5vw;
    }
    .dropdown {
  transition: 0.3s;

  position: absolute;
  top: 120%;
  right: 0;
  left: 0;

  margin: 0;
  padding: 0;

  list-style: none;

  z-index: 99;

  border-radius: 15px;
  box-shadow: inherit;
  background: rgba(255,255,255,0.06);
backdrop-filter: blur(5.6px);
  -webkit-transform-origin: top;
  -moz-transform-origin: top;
  -ms-transform-origin: top;
  transform-origin: top;

  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;

  opacity: 0;
  visibility: hidden;
}
  .dropdown li {
  padding: 0 15px;
  line-height: 45px;
  overflow: hidden;
}
.dropdown li:last-child {
  border-bottom: none;
}

.dropdown {
  padding: 0.5rem !important;
}
.dropdown li:hover {
  background-color: rgba(255,255,255,0.06);
  border-radius: 10px;
}
.select-container.active .dropdown {
  opacity: 1;
  visibility: visible;
  overflow-y: scroll;
  height: 15vw  ;
  border-radius: 15px;
}

.selected-display {
  margin-left: 10px;
  margin-top: 25px;
}
@media only screen and (max-width:765px){
    .select-container{
        width: 71.5%;
        margin-top: 2.5vw;
        border-radius: 10px;
    }
    .select-container.active .dropdown{
        height: 45vw;
    }
}
</style>
