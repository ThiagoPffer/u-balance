<template>
    <div class="table-container">
        <table v-if="transactionsList.length != 0">
            <tr>
                <th>Valor</th>
                <th>Descrição</th>
                <th>Tipo</th>
                <th>Data</th>
                <th></th>
            </tr>
            <tr v-for="transaction in transactionsList" v-bind:key="transaction" title="Ver detalhes">
                <td> {{transaction.amount}} </td>
                <td> {{transaction.description}} </td>
                <td> {{transaction.type}} </td>
                <td> {{transaction.date}} </td>
                <td>
                    <button class="button-table">Ver</button>
                    <button @click="removerItem(transaction)" class="button-close" title="Excluir item"><span class="mdi mdi-close"></span></button> 
                </td>
            </tr>
        </table>
        <p v-if="transactionsList.length === 0">Não há nenhum item a ser exibido</p>
    </div>
</template>

<script>
    import _isEmpty from 'lodash/isEmpty';
    export default {
        name: 'DefaultTable',
        props: {
            transactionsListProps: Array
        },
        data() {
            return {
                transactionsList: this.transactionsListProps
            };
        },
        methods: {
            removerItem(item) {
                if(!_isEmpty(this.transactionsList)) {
                    this.transactionsList.splice(this.transactionsList.indexOf(item), 1);
                }
            },
        }
    };
</script>

<style scoped>
    .table-container {
        display: flex;
        align-items: center;
        justify-content: center;
        background: #fff;
        border-radius: 8px;
        min-width: 55rem;
        height: auto;
        box-shadow: rgba(0, 0, 0, 0.1) 0 0 80px;
        box-sizing: border-box;
        padding: 15px 0;
    }

    .table-container table {
        align-self: flex-start;
        border-collapse: collapse;
        width: 100%;
    }

    .button-close {
        font-size: 1.2rem;
    }

    .button-close:hover {
        color: var(--red);
    }

    .button-table {
        color: #fff;
        height: 100%;
        width: 60px;
        background: var(--primary);
        border-radius: 4px;
        margin-right: 15px;
        padding: 6px 0;
    }

    .button-table:hover{
        background: var(--primary-dark);
    }

    .test {
        font-weight: 200;
    }
</style>