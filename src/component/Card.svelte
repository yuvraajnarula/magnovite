<script>
    export let title = '';
    export let description = '';
    export let link = '#';
    export let tag = '';
    export let img="";
</script>
<div class="card-component">
    <img src="{img}" alt="{description}">
    <input type="hidden" class="s" value="{tag}">
    <h2 class="card-title">{title}</h2>
    <p>{description.length > 100 ? description.slice(0, 100) + '...' : description}</p>
    <a href="{link}" target="_blank" rel="noopener noreferrer" style="text-decoration: none;"><span>Learn more</span></a>
</div>
<style>
    .card-component img{
        width: 95%;
        margin: 10px auto;
        border-radius: 10px;
        height: auto;
    }
</style>