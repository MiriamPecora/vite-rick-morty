<script>
    import axios from 'axios';
    import { store } from '../store';
    export default {
        name: "ListApp",
        data() {
            return {
                store,
            };
        },
        created() {
            axios
            .get("https://rickandmortyapi.com/api/character")
            .then((response) => {
                
                response.data.results.forEach(character => {
                    this.store.push(
                        {
                            name: character.name,
                            status: character.status,
                            species: character.species, 
                        }
                    )
                });

                console.log(this.store, "store");
            });
        },
    };
</script>
<template>

</template>