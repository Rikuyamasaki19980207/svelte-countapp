<script lang="ts">
  import {card} from './card.ts';

  //マイナスロジック
  const minusItem = cart => {
    for (let item of $card) {
      if (item.id === cart.id) {
        if (cart.quantity > 0) cart.quantity -= 1;   
        $card = $card;
        cart.quantity = cart.quantity;
        return;
      }
    }
  };

  //プラスロジック
  const plusItem = cart => {
    for (let item of $card) {
      if (item.id === cart.id) {
        cart.quantity += 1;
        $card = $card;
        return;
      }
    }
  };

  //リセットロジック
  const resetItem = cart => {
    for (let item of $card) {
      if (item.id === cart.id) {
        cart.quantity = 0;
        $card = $card;
        return;
      }
    }
  };

  //カード削除ロジック
  const removeToCard = cart => {
    $card = $card.filter(cartItem => cartItem != cart);
  };
</script>

<div class="card">
  {#each $card as item}
    <div class="card-body">
      <div class="cart-item">
        <input class="card-input" bind:value={item.address} />
        <span class="card-text">{item.quantity}</span>
        <button class="card-pulus" on:click={() => plusItem(item)}>+</button>
        <button class="card-minus" on:click={() => minusItem(item)}>-</button>
        <button class="card-reset" on:click={() => resetItem(item)}>0</button>
        <button class="card-delete" on:click={() => removeToCard(item)}
          >x</button
        >
      </div>
    </div>
  {/each}
</div>

<style>
  @media (max-width: 1500px){
  .cart-item {
    border: 2px solid #0000;
    width: 385px;
    height: 36.5px;
    border-radius: 5px;
    box-shadow: 0 4px 6px 0 #00000033;
    margin: 0 auto;
    background-color: #f0f3fafb;
  }

  .card {
    text-align: center;
  }

  .card-input {
    width: 8rem;
    margin-left: 1.438px;
    margin-right: 1.5rem;
    box-sizing: border-box;
    border-width: 0;
    border-style: solid;
    border-color: #e2e8f0;
    color: #718096;
    height: 25px;
  }

  .card-text {
    font-size: 1.125rem;
    font-weight: 700;
    padding-left: 1rem;
    padding-right: 3rem;
  }

  .card-pulus {
    border-top-left-radius: 0.25rem;
    border-bottom-left-radius: 0.25rem;
    background-color: #f56565;
    border-color: #f56565;
    color: #fff;
    cursor: pointer;
    width: 35px;
    margin-right: 2px;
  }

  .card-pulus:active {
    background: #f56565;
    border-color: #0b3cdb;
  }

  .card-minus {
    background-color: #4299e1;
    border-color: #4299e1;
    color: #fff;
    cursor: pointer;
    width: 35px;
    margin-left: -6.2px;
  }

  .card-minus:active {
    background: #4299e1;
    border-color: #0b3cdb;
  }

  .card-reset {
    border-top-right-radius: 0.25rem;
    border-bottom-right-radius: 0.25rem;
    background-color: #ecc94b;
    border-color: #ecc94b;
    color: #fff;
    cursor: pointer;
    width: 37px;
    margin-left: -4.2px;
    font-size: 1rem;
  }

  .card-reset:active {
    background: #ecc94b;
    border-color: #0b3cdb;
  }

  .card-delete {
    border-color: #f0f3fafb;
    color: #a0aec0;
  }

  .card-delete:active {
    background: #f0f3fafb;
  }
  }

  @media (max-width: 450px){
  .cart-item {
    border: 2px solid #0000;
    width: 385px;
    height: 36.5px;
    border-radius: 5px;
    box-shadow: 0 4px 6px 0 #00000033;
    margin: 0 auto;
    background-color: #f0f3fafb;
  }



  .card {
    text-align: center;
  }

  .card-input {
    width: 8rem;
    margin-left: 1.438px;
    margin-right: 1.5rem;
    box-sizing: border-box;
    border-width: 0;
    border-style: solid;
    border-color: #e2e8f0;
    color: #718096;
    height: 25px;
  }

  .card-text {
    font-size: 1.125rem;
    font-weight: 700;
    padding-left: 1rem;
    padding-right: 3rem;
  }

  .card-pulus {
    border-top-left-radius: 0.25rem;
    border-bottom-left-radius: 0.25rem;
    background-color: #f56565;
    border-color: #f56565;
    color: #fff;
    cursor: pointer;
    width: 35px;
    margin-right: 2px;
  }

  .card-pulus:active {
    background: #f56565;
    border-color: #0b3cdb;
  }

  .card-minus {
    background-color: #4299e1;
    border-color: #4299e1;
    color: #fff;
    cursor: pointer;
    width: 35px;
    margin-left: -6.2px;
  }

  .card-minus:active {
    background: #4299e1;
    border-color: #0b3cdb;
  }

  .card-reset {
    border-top-right-radius: 0.25rem;
    border-bottom-right-radius: 0.25rem;
    background-color: #ecc94b;
    border-color: #ecc94b;
    color: #fff;
    cursor: pointer;
    width: 37px;
    margin-left: -4.2px;
    font-size: 1rem;
  }

  .card-reset:active {
    background: #ecc94b;
    border-color: #0b3cdb;
  }

  .card-delete {
    border-color: #f0f3fafb;
    color: #a0aec0;
  }

  .card-delete:active {
    background: #f0f3fafb;
  }
  }

</style>
