<script>
    export let title = '';
    export let description = '';
    export let link = '#';
    export let tag = '';
</script>
<div class="card-component">
    <input type="hidden" class="s" value="{tag}">
    <h2 class="card-title">{title}</h2>
    <p>{description.length > 100 ? description.slice(0, 100) + '...' : description}</p>
    <a href="{link}" target="_blank" rel="noopener noreferrer" style="text-decoration: none;"><span>Learn more</span></a>
</div>