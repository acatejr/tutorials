<script>
    export let showModal = false
    // export let message = "Default value."
    export let isPromo = false
</script>

{#if showModal}
<!-- event forwarding by registering event, but not setting it equal to anything. -->
<!-- |self is the event modifier.  It is a type of event modifier.  There are others. -->
<div class='backdrop' class:promo={isPromo} on:click|self>
    <div class='modal'>
        <slot></slot>
    </div>
</div>
{/if}

<!--- component specific styles -->
<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8)
    }

    .modal {
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background: white;
    }

    .promo .modal {
        background: crimson;
        color: white;
    }
</style>