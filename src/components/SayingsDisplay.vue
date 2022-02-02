<template>
    <div class="sayingsDisplay">
        <button @click="sayClicked">ticketyboo</button>
        <button @click="tickDown">prev saying</button>
        <button @click="tickUp">next saying</button>
        {{this.saying}}
    </div>
</template>

<script>
export default {
    name: 'SayingsDisplay',
    props: {
        saying: String
    },
    methods: {
        sayClicked() {
            console.log("I've been clicked!!!");
        },
        tickUp(){
            console.log("say the next thing");
            this.$emit("next");
        },
        tickDown(){
            console.log("say the previous thing");
            this.$emit("previous");
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
