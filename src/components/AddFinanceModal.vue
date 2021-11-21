<template>
    <div class="modal-mask">
        <div class="modal-wrapper">
            <div class="modal-container">
                <div class="modal-header">
                    <h2>Adicionando Movimentação</h2>
                </div>

                <div class="modal-body">
                    <div class="input-group">
                        <label class="default-label" for="input-descricao">Descrição</label>
                        <input class="default-input" type="text" id="input-descricao" placeholder="Descreva a movimentação">
                    </div>
                    <div class="row-container gap-horizontal--16">
                        <div class="input-group">
                            <label class="default-label" for="input-data">Data</label>
                            <input class="default-input" type="date" id="input-data" placeholder="Data da movimentação">
                        </div>
                        <div class="input-group">
                            <label class="default-label" for="input-valor">Valor</label>
                            <input class="default-input" type="number" id="input-valor" placeholder="Valor movimentado">
                        </div>
                    </div>
                </div>

                <div class="modal-footer">
                    <button class="default-button" @click="$emit('close')">Salvar</button>
                    <button class="no-background-button" @click="$emit('close')">Cancelar</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AddFinanceModal',
    data() {
        return {

        }
    }
}
</script>

<style>
    .modal-mask {
        position: fixed;
        z-index: 9998;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        background-color: rgba(0, 0, 0, 0.5);
        animation-name: modal-mask-animation;
        animation-duration: .4s;
        display: table;
    }

    @keyframes modal-mask-animation {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    .modal-wrapper {
        display: table-cell;
        vertical-align: middle;
    }

    .modal-container {
        width: 600px;
        margin: 0px auto;
        padding: 25px;
        background-color: #fff;
        border-radius: 8px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
        animation-name: modal-animation;
        animation-duration: .4s;
    }

    @keyframes modal-animation {
        from {
            transform: scale(60%);
            opacity: 0;
        }
        to {
            transform: scale(100%);
            opacity: 1;
        }
    }

    .modal-header h2 {
        margin-top: 0;
        color: var(--black);
        text-align: left;
    }

    .modal-body {
        display: flex;
        flex-direction: column;
        gap: 16px;
        margin: 20px 0;
    }

    .modal-footer {
        display: flex;
        flex-direction: row;
        gap: 16px;
        margin-top: 32px;
    }

    .modal-default-button {
        display: block;
        margin-top: 1rem;
    }

    .input-group{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        flex: 1;
    }

    .default-label {
        font-size: 1rem;
        color: var(--black);
        margin-bottom: 6px;
    }

    .default-input {
        color: var(--black);
        padding: 10px 15px;
        border: 1px solid var(--primary);
        border-radius: 4px;
        box-shadow: transparent 0 5px 10px;
        width: 100%;
        transition: .3s ease-out;
    }

    .default-input:focus {
        border: 1px solid transparent;
        box-shadow: rgba(0, 0, 0, 0.1) 0 5px 10px;
    }

    .default-button {
        font-size: 1rem;
        color: #fff;
        border-radius: 8px;
        background: var(--primary);
        padding: 15px;
        width: 100%;
        transition: .3s;
    }

    .default-button:hover {
        background: var(--primary-dark);
    }

    .no-background-button {
        font-size: 1rem;
        color: var(--primary);
        border: 1px solid transparent;
        border-radius: 8px;
        padding: 15px;
        width: 100%;
        transition: .3s;
    }

    .no-background-button:hover {
        border: 1px solid var(--primary-dark);
    }
</style>