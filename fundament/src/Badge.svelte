<svelte:options tag="twopine-badge" />


<script>
    export let icon, type;
</script>

<p class="{type}"><i class="fa-solid fa-{icon}"></i><slot/></p>

<style>
    p {
        color: #fff;
        padding: var(--padding);
    }

    p.primary {
        background: var(--color-primary);
    }

    p.secundary {
        border: var(--color-primary) var(--border-width) var(--border-style);
        color: var(--color-primary);
        background: transparent;
    }
</style>
