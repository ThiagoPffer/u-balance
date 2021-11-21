<template>
    <button class="default-button"> <span class="mdi" v-bind:class="classObject"></span> {{ buttonText }}</button>
</template>

<script>
export default {
    name: 'ButtonText',
    data() {
        return {
            classObject: 'mdi-plus',
            buttonText: 'Adicionar'
        }
    }
}
</script>

<style scoped>
    .default-button {
        border-radius: 8px;
        background: #fff;
        font-size: 1rem;
        font-weight: 500;
        color: var(--primary-dark);
        width: 250px;
        padding: 15px;
        transition: ease-out .3s;
    }

    .default-button:hover {
        background: var(--primary-lighter);
    }
</style>