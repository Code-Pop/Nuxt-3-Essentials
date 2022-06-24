<script setup>
const route = useRoute()
const { data: coin } = await useFetch('/api/ticker?id=' + route.params.id)
</script>

<template>
  <div>
    <h2>{{ coin[0].name }} Detail page</h2>
    <table border="1 px solid">
      <thead>
        <th>Symbol</th>
        <th>Rank</th>
        <th>Price - US $</th>
        <th>Market Cap - US $</th>
      </thead>
      <tr>
        <td>{{ coin[0].symbol }}</td>
        <td>{{ coin[0].rank }}</td>
        <td>{{ coin[0].price_usd }}</td>
        <td>{{ coin[0].market_cap_usd }}</td>
      </tr>
    </table>
  </div>
</template>
