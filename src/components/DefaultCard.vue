<template>
    <div class="default-card-container">
        <h3 class="card-title">Entradas</h3>
        <span class="card-balance"><span class="card-currency">R$</span> 24444,00</span>
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
        background: #fff;
        min-width: 250px;
        height: auto;
        padding: 20px 45px 20px 25px;
        box-sizing: border-box;
        user-select: none;
        cursor: pointer;
        transition: ease-out .3s;
    }

    .default-card-container:hover {
        background: var(--primary-lighter);
    }

    .card-title,
    .card-currency {
        font-weight: 400;
    }

    .card-balance {
        font-size: 3rem;
        font-weight: 500;
    }
</style>