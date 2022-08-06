<script lang="ts">
  import {card} from './card.ts';
  interface countObj {
    id: number;
    quantity: number;
    address: string;
  };

  //カード追加ロジック
  const addToCard = () => {
    const counter: countObj = {
      id: 1 + Math.floor(Math.random() * 100),
      quantity: 0,
      address: 'new'
    };

    $card = [...$card, counter];
  };
</script>

<div class="product-list">
  <button on:click={() => addToCard()}>new counter</button>
</div>

<style>
  .product-list {
    margin: auto;
  }

  button {
    width: 384px;
    text-align: center;
    height: 24px;
    cursor: pointer;
    line-height: 0;
    padding: 5px 0;
    --bg-opacity: 1;
    background-color: #68d391;
    border-color: #68d391;
    background-color: rgba(104, 211, 145, var(--bg-opacity));
    --text-opacity: 1;
    color: #fff;
    color: rgba(255, 255, 255, var(--text-opacity));
  }

  button:active {
    background: #68d391;
  }
</style>
