<template>
    <div class="list-wrapper">
        <div class="list" v-for='candidate in filteredByID' v-bind:key='candidate.id'>
            <ListItem v-bind:candidate='candidate'/>
        </div>
    </div>
</template>

<script>
import ListItem from './ListItem';
import axios from 'axios';

export default {
    name: 'List',
    components: {
        ListItem,
    },
    data() {
        return {
            candidates: []
        }
    },
    methods: {
        getPpl() {
            prompt(this.candidates);
        }
    },
    created() {
        axios.get('http://localhost:8080/users/v1/get_users')
            .then(res => this.candidates = res.data)
            .catch(err => err);
    },
    computed: {
        filteredByID() {
            return this.candidates.filter(candidate => candidate.id % 2 === 0);
        }
    }
}
</script>

<style scoped>
    .list-wrapper {
        width: 100%;
        overflow-y: scroll;
    }
    
    .list {
        display: flex;
        flex-direction: column;
        width: 100%;
        align-items: center;
    }
</style>



