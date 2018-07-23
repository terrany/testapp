<template>
    <div id="app">
        <Form :fields="[person.name, person.age]"/>
        <Form :fields="[person.name, person.weight]"/>
        <Form :fields="[person.name, person.height]"/>
    </div>
</template>

<script>

    import Vue from 'vue';
    import Form from './components/Form';
    import VModal from 'vue-js-modal';

    Vue.use(VModal, {dynamic: true, injectModalsContainer: true});
    export default {
        name: 'App',
        data() {
            return {
                person: {
                    name: {
                        title: 'Ф.И.О.',
                        value: null
                    },
                    age: {
                        title: 'Возраст',
                        value: null
                    },
                    weight: {
                        title: 'Вес',
                        value: null
                    },
                    height: {
                        title: 'Рост',
                        value: null
                    }
                }
            }
        },
        components: {
            VModal,
            Form
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
