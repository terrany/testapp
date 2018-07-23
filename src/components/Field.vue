<template>
    <div class="form-group">
        <label>{{title}}:</label>
        <input type="text" placeholder="" :value="value" @input="$emit('update:value', $event.target.value)">
    </div>
</template>

<script>
    export default {
        name: 'Field',
        props: ['title', 'value']
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .form-group {
        display: flex;
        margin: 20px;
    }

    label {
        width: 80px;
        align-self: center;
    }

    input {
        padding: 5px 10px;
        border-radius: 4px;
        border: 3px solid #eaeaea;
    }

    input:focus {
        border: 3px solid #a8a8a8;
        outline: none;
    }
</style>
