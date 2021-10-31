<template>
    Square of selected value: {{double}}
</template>
<script>
export default {
    props: ["original"],
    data() {
        return {
            double: this.original*this.original
        }
    },
    watch: {
        original: function (newValue) {
            console.log("new value in component", newValue)
            this.double = newValue*newValue;
        }
    }
}

</script>
<style>

</style>
