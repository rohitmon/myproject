<script>
    export let isPromo  = true;
    export let showModal  = true;
</script>

{#if showModal }
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="backdrop" class:promo={isPromo} on:click|self>
        <div class="modal">
            <slot></slot>
        </div>
    </div>
{/if}

<style>
    .backdrop{
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8);
    }
    .modal {
        padding: 10px;
        background: white;
    }
    .promo .modal {
        background: red;
    }
</style>