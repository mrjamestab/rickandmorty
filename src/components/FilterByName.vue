<template>
    <div class="search">
        <input type="text" placeholder="Busca por nombre"
        @keyup="filter()" v-model="name">
    </div>
    </template>
    
    <script>
    import { useStore } from 'vuex';
    import { ref } from 'vue';
    export default{
        setup(){
            const store = useStore();
            const name = ref('')
            const filter = () => {
                store.dispatch('filterByName', name.value);
            }
    
            return { filter, name }
        }
    }
    
    </script>
    
    <style lang="scss">
    .search{
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 30px 0px;
        font-size: 1rem;
        font-family: sans-serif;
        
        input {
        font-size: 1rem;
        background-color: #212121;
        width: 390px;
        margin-left: 10px;
        padding: 10px 15px;
        color: white;
         text-align: center;
        border: 2px solid white;
        border-radius: 5px;
        /* box-shadow: 3px 3px 2px rgb(249, 255, 85); */
        }

        input:focus {
        color: rgb(0, 255, 255);
        background-color: #212121;
        outline-color: rgb(0, 255, 255);
        box-shadow: -3px -3px 15px rgb(0, 255, 255);
        transition: .1s;
        transition-property: box-shadow;
        }
    }
    </style>
    