<template>
    <div class="table-container">
        <table>
            <tr>
                <th>Valor</th>
                <th>Descrição</th>
                <th>Tipo</th>
                <th>Data</th>
                <th></th>
            </tr>
            <tr v-for="item in array" v-bind:key="item" title="Ver detalhes">
                <td> {{item.valor}} </td>
                <td> {{item.descricao}} </td>
                <td> {{item.tipo}} </td>
                <td> {{item.data}} </td>
                <td>
                    <button class="button-table">Ver</button>
                    <button @click="removerItem(item)" class="button-close" title="Excluir item"><span class="mdi mdi-close"></span></button> 
                </td>
            </tr>
        </table>
        <p v-if="array.length === 0">Não há nenhum item a ser exibido</p>
    </div>
</template>

<script>
    export default {
        name: 'DefaultTable',
        data() {
            var array = []
            let i = 0;
            while (i < 10) {
                array.push({
                    valor: '460,00',
                    descricao: 'descrição',
                    tipo: 'ENTRADA',
                    data: Date.now(),
                    id: i
                });
                i++;
            }
            return {
                array,
            };
        },
        methods: {
            removerItem(item) {
                console.log(item);
                this.array.splice(this.array.indexOf(item), 1);
            },
        }
    };
</script>

<style scoped>
    .table-container {
        background: #fff;
        border-radius: 8px;
        min-width: 55rem;
        height: auto;
        box-shadow: rgba(0, 0, 0, 0.1) 0 0 80px;
        box-sizing: border-box;
        padding: 15px 0;
    }

    .table-container table {
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