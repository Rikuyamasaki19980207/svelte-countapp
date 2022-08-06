<script lang="ts">
  import {card} from './card.ts';
</script>

<div>title list: {$card.map(x => x.address).join(', ')}</div>
<div>sum of count: {$card.reduce((sum, item) => sum + item.quantity, 0)}</div>
