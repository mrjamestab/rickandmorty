<template>
    <section>
        <h2>Characters</h2>
        <div class="characters">
            
            <div class="characters__item" v-for="character in characters" :key="character.id" >
               <CardCharacter :character="character"/>
            </div>
        </div>
    </section>
</template>

<script>
import { onMounted, computed } from 'vue';
import { useStore } from 'vuex';
import CardCharacter from '@/components/CardCharacter.vue';
export default{
    setup() {
        const store = useStore();
        const characters = computed(() => {
            return store.state.charactersFilter;
        });
        onMounted(() => {
            store.dispatch("getCharacters");
        });
        return {
            characters
        };
    },
    components: { CardCharacter }
}

</script>

<style lang="scss">
.characters{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;

}    


</style>
