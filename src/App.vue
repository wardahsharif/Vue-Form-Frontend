<script setup>
import {ref} from 'vue';

function increment() {
count.value++
}


const count = ref(0)

</script>


<template>
<h1>Counter App</h1>
<button @click="increment">Increment</button>
<p>count: {{count}}</p>
</template>
 