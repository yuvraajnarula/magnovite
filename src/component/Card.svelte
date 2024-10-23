<script>
    export let title = '';
    export let description = '';
    export let link = '#';
</script>
<div class="card-component">
    <h2>{title}</h2>
    <p>{description.length > 100 ? description.slice(0, 100) + '...' : description}</p>
    <span aria-label="{link}">Learn more</span>
</div>