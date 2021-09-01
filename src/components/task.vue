<template>
<div>
    <table>
        <tr v-for="product in products" v-bind:key="product.id">
            <td><img v-bind:src="product.imgUrl" width="300"> </td>
            <td>{{product.name}}</td>
            <td>{{product.price}}</td>
        </tr>
    </table>
</div>
</template>
<script>

export default {
    name: "Task-axios",    
    data(){
        return{products:[]}
    },
    mounted(){
        fetch('http://localhost:3000/products')
        .then(response=> response.json())
        .then(data => this.products = data)
        .catch(err=>err.message)

    }
}
</script>