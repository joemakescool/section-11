<template>
    <div>
        <h1>Joe</h1>

        <div
            id="on"
            @click="switched(true)"
            :class="{active: value}"
        >
            ON
        </div>

        <div
            id="off"
            @click="switched(false)"
            :class="{active: !value}"
        >
            OFF

        </div>


    </div>

</template>

<script>
    export default {
        name: "Joe",
        data(){
            return{
                isOn: true,

            }
        },
        props: ['value'],

        methods: {
            switched(change) {
                this.$emit('input', change);
                // eslint-disable-next-line no-console
                console.log(change);
            }
        }
    }
</script>

<style scoped>
    #on, #off {
        width: 40px;
        height: 20px;
        background-color: lightgray;
        padding: 2px;
        display: inline-block;
        margin: 10px -2px;
        box-sizing: content-box;
        cursor: pointer;
        text-align: center;
    }

    #on:hover, #on.active {
        background-color: lightgreen;
    }

    #off:hover, #off.active {
        background-color: lightcoral;
    }
</style>
