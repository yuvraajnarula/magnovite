<script>
    export let title = '';
    export let description = '';
    export let link = '#';
</script>
<div class="card-component">
    <h2>{title}</h2>
    <p>{description.length > 100 ? description.slice(0, 100) + '...' : description}</p>
    <a href="{link}" target="_blank" rel="noopener noreferrer" style="text-decoration: none;"><span>Learn more</span></a>
</div>