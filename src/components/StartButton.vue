<template>
    <button class="get__start__btn" @click="start">Начать</button>
</template>

<script>
export default {
    methods: {
        start() {
            this.$emit('start');
        }
    }
}
</script>

<style>
.get__start__btn {
    box-sizing: border-box;
    padding: 5px 12px;

    border-radius: 6px;
    background-color: #4F82E5;
    transition: 0.2s;

    font-size: 24px;
    font-weight: 500;
    color: #fff;
    user-select: none;
    -webkit-user-select: none;
}

.get__start__btn:active {
    transform: scale(0.97);
}
</style>