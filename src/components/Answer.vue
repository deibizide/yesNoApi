<template>
    <div class="hello" id="full">
        <h1>{{ answer.toUpperCase() }}!</h1>
        <img :src="imgUrl" id="bg" />
    </div>
</template>

<script>
const axios = require('axios');

export default {
    data() {
        return {
            imgUrl: null,
            answer: null,
        };
    },

    mounted() {
        axios
            .get('https://yesno.wtf/api')
            .then(resp => {
                this.imgUrl = resp.data.image;
                this.answer = resp.data.answer;
                console.log(resp.data.image);
                console.log(resp.data.answer);
            })
            .catch(error => console.log(error));
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
html,
body {
    height: 100%;
    margin: 0px;
    padding: 0px;
}
#full {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 200px;
    height: 100vh;
}

#bg {
    position: fixed;
    top: 0;
    left: 0;

    /* Preserve aspet ratio */
    min-width: 100%;
    min-height: 100%;
    z-index: -1;
}
</style>
