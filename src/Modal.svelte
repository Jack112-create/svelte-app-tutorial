<script>
  export let message;
  let shoModal = true;
  export let isPromo = false;
</script>

{#if shoModal}
  <div class="backdrop" class:promo={isPromo}>
    <div class="modal">
      <p>{message}</p>
    </div>
  </div>
{/if}

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.8);
  }

  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background: #fff;
  }

  .promo .modal {
    background: crimson;
    color: #fff;
  }
</style>