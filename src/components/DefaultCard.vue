<template>
    <div class="default-card-container">
        <h3>Entradas</h3>
        <span class="text-finance">R$ 244,00</span>
    </div>
</template>

<script>
    export default {
        name: 'DefaultCard',
        data() {
            return {

            }
        }
    }
</script>

<style scoped>
    .default-card-container {
        display: flex;
        align-items: flex-start;
        justify-content: center;
        flex-direction: column;
        border-radius: 8px;
        background: rgb(255, 255, 255);
        min-width: 250px;
        height: 110px;
        padding: 20px 25px;
        box-sizing: border-box;
        box-shadow: rgba(0, 0, 0, 0.1) 0 0 10px;
        user-select: none;
        cursor: pointer;
        transition: ease-out .3s;
    }

    .default-card-container:hover {
        background: var(--primary-lighter);
    }

    .text-finance {
        font-size: 2rem;
    }
</style>