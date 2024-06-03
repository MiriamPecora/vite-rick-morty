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
                            image: character.image,
                        }
                    )
                });

                console.log(this.store, "store");
            });
        },
    };
</script>
<template>
    <div class="card" v-for="person in store">
        <img :src="person.image" :alt="person.name">
        <h2> {{ person.name }} </h2>
        <p> {{ person.status }} </p>
        <p class="species"> {{ person.species }} </p>
    </div>
</template>