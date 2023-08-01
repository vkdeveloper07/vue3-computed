<template>
    <div class="container">
        <h1>Books Details</h1>
        <p>Number of books in library {{ books.length }}</p>
        <p>Number of Books under 300 RS </p> <br>
        <ul>
            <li v-for="book in booksUnder300Rs">{{ book }}</li>
        </ul>
    </div>
</template>

<script setup>
import {ref,computed} from 'vue';
const books = ref([
    {name:'Atomc Habits', price: 460},
    {name:'Rich Dad Poor Dad', price: 350},
    {name:'Deep Work', price: 276},
    {name:'The One Thing', price:240}
])

const booksUnder300Rs = computed(()=>{
    return books.value.filter(book => book.price <= 300).map(book => book.name);
})
</script>

<style scoped>
.container{
    margin: auto;
    width: 500px;
    border: 1px solid white;
    text-align: center;
}
</style>