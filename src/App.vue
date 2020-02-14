<template>
    <div id="app">
        <Answer />
    </div>
</template>

<script>
import Answer from './components/Answer.vue';

export default {
    name: 'App',
    components: {
        Answer,
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    color: #2c3e50;
}
</style>
