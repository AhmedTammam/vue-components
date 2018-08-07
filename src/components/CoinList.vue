<template>
    <div class="table-responsive-sm">
        <table class="table table-hover table-bg">
            <thead class="thead text-center btn-primary">
                <tr>
                <th scope="col">Name</th>
                <th scope="col">Market Cap</th>
                <th scope="col">Price</th>
                <th scope="col">Volume(24h)</th>
                <th scope="col">Circulating Supply</th>
                <th scope="col">change(24h)</th>
                </tr>
            </thead>
            <tbody class="text-center" v-if="filteration.length">
                <tr v-for="coin in filteration">
                    <td>{{coin.name}}</td>
                    <td>{{coin.market_cap_usd}}</td>
                    <td>{{coin.price_usd}}</td>
                    <td>{{coin['24h_volume_usd']}}</td>
                    <td>{{coin.available_supply}}</td>
                    <td>{{coin.percent_change_24h}}</td>
                </tr>
            </tbody>
            <tbody class="text-center" v-else="filteration.length">
                <tr v-for="coin in coins">
                    <td>{{coin.name}}</td>
                    <td>{{coin.market_cap_usd}}</td>
                    <td>{{coin.price_usd}}</td>
                    <td>{{coin['24h_volume_usd']}}</td>
                    <td>{{coin.available_supply}}</td>
                    <td>{{coin.percent_change_24h}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    props: ['coins', 'filteration']
}
</script>

<style>
    .table-bg{
     background-color: white;
     font-size: 18px;
    }
</style>
