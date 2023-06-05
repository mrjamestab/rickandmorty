<template>
<div class="filter">
    <div class="item" @click="filter('')">All</div>
    <div class="item" @click="filter('Alive')">Alive</div>
    <div class="item" @click="filter('Dead')">Dead</div>
    <div class="item" @click="filter('unknown')">Unknown</div>
</div>
</template>

<script>
import { useStore } from 'vuex';

export default{
    setup(){
        const store = useStore();

        const filter = ((status) => {
            store.dispatch('filterByStatus', status);
        })

        return { filter }
    }

}
</script>

<style lang="scss">
.filter{
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px 0;
    .item{
        text-transform: uppercase;
        width: 100px;
        height: 30px;
        background-color: var(--background-card);
        color: var(--text-gray);
        border-radius: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0 10px;
        cursor: pointer;
        transition: transform 200ms ease-in-out;
        &:hover{
            transform: scale(1.05);
            background-color: var(--text-gray);
            color: var(--background-card);
            transition: transform 200ms ease-in-out, background-color 200ms ease-in-out, color 200ms ease-in-out;
        }
    }

}
</style>
