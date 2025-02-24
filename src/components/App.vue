<template>
    <div id="app" class="container-fluid">
        <div class="row text-center justify content-center align-items-center vh-100">
            <div class="col-sm-7">
                <h1 class="off-white title-size">Incrementer</h1>
            </div>
            <div class="col-sm-4">
                <p>Incrementer is a simple Vue.js app that lets users adjust and add customizable increments to a counter. With intuitive controls, you can increase or decrease the increment value, apply it to the count, and reset everything with a single click. Perfect for quick calculations and tracking numbers efficiently.</p>
            </div>
        </div>
        <div id="main" class="row text-center justify-content-center align-items-center vh-100">
            <div class="col">
                <p>current increment: {{ inc }}</p>
                <button @click="inc--">-</button><input v-model="inc" placeholder="increment"/><button @click="inc++">+</button>
            </div>
            <div class="col">
                <h3 class="off-white">Count: {{ count }}</h3>
                <br>
                <button @click="count += Number(inc)">Add</button>
            </div>
            <div class="col">
                <button @click="reset()">Reset</button>
            </div>
        </div>
    </div>
</template>

<script>
    import { ref } from 'vue';
    export default {
        setup() {
            const count = ref(0);
            const inc = ref(1);
            
            function reset() {
                count.value = 0;
                inc.value = 1;
            }
            return { count, inc, reset }
        },
    }
</script>