<svelte:options tag="twopine-button" />

<script>
    import { get_current_component } from "svelte/internal";
    export let type;
    export let disabled = false;

    const thisComponent = get_current_component();

    const dispatchEvent = (name, detail) => {
        thisComponent.dispatchEvent(
            new CustomEvent(name, {
                detail,
                composed: true
            })
        );
    };

    function handleClick(event) {
        event.preventDefault();
        dispatchEvent("customClick", name);
        console.log('log')
    }

</script>

<button class={type} {disabled} on:click="{handleClick}">
    <slot />
</button>

<style>
    button {
        transition: ease-in-out 0.2s all;
        box-sizing: content-box;
        padding: var(--padding);
        color: white;
        font-size: var(--font-size);
        border-radius: var(--border-radius);
        border-width: var(--border-width);
        border-style: var(--border-style);
        border-color: var(--color-primary);
        cursor: pointer;
    }

    button:disabled,
    button[disabled] {
        border: 1px solid #999999;
        background-color: #cccccc;
        color: #666666;
        cursor: not-allowed;
    }

    button.primary:disabled:hover,
    button.secundary:disabled:hover,
    button.outline:disabled:hover {
        filter: unset;
        color: #666666;
    }

    button.primary {
        background: var(--color-primary);
        border-color: var(--color-primary);
    }

    button.primary:hover {
        transition: ease-in-out 0.2s all;
        filter: brightness(var(--hover-brightness));
    }

    button.secundary {
        background: var(--color-secundary);
        border-color: var(--color-secundary);
    }

    button.secundary:hover {
        transition: ease-in-out 0.2s all;
        filter: brightness(var(--hover-brightness));
    }

    .outline {
        color: var(--color-primary);
        background: transparent;
    }

    button.outline:hover {
        transition: ease-in-out 0.2s all;
        color: white;
        filter: brightness(var(--hover-brightness));
    }
</style>
