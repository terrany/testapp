<template>
    <form>
        <Field v-for="field in fields" :value.sync="field.value" :title="field.title"></Field>
        <button @click.prevent="show">Сохранить</button>
    </form>
</template>

<script>
    import Field from './Field';

    export default {
        name: 'Form',
        props: ['fields'],
        components: {
            Field,
        },
        methods: {
            show() {
                this.$modal.show({
                    template: `
                        <div class="modal">
                            <h1>Форма</h1>
                            <ol>
                                <li v-for="field in fields" v-if="field.value">{{field.title}}: <b>{{field.value}}</b></li>
                            </ol>
                        </div>
  `,
                    props: ['fields']
                }, {
                    fields: this.fields
                }, {
                    height: 'auto'
                })
            }
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
    form {
        display: table;
        border: 5px dashed #e28a93;
        margin: 0 auto 30px;
        padding: 20px 0;
    }

    button {
        cursor: pointer;
        border-radius: 4px;
        background: #ffef2c;
        color: #333;
        font-weight: bold;
        border: none;
        padding: 7px 20px;
        box-shadow: 0 1px 2px #999;
        text-transform: uppercase;
    }

    button:active {
        box-shadow: none;
    }

    button:focus {
        outline: none;
    }

    .modal {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        padding: 10px 25px;
    }
</style>
