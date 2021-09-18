<script>
    import { fly } from 'svelte/transition';
    export let refresh = '';
</script>

{#key refresh}
    <div in:fly={{ duration: 300, delay: 300 }} out:fly={{ duration: 300}}>
        <slot />
    </div>
{/key}