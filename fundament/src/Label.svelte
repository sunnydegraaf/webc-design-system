<svelte:options tag="twopine-label" />

<script>
    export let type = "secundary";
</script>

<span class="label {type == "secundary" ? "secundary" : "primary"}">
    <slot />
</span>

<style>
    .label {
        font-weight: 800;
        position: absolute;
        top: 5%;
        left: -10px;
        color: var(--color-neutral-tint-100);
        padding: 10px;
    }

    .label.primary {
        background: var(--color-primary);
    }

    .label.secundary {
        background: var(--color-secundary);
    }
</style>