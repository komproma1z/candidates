<template>
    <div class="list-wrapper">
        <div class="list" v-for='candidate in sortByName' v-bind:key='candidate.id'>
            <ListItem v-bind:candidate='candidate'/>
        </div>
    </div>
</template>

<script>
import ListItem from './ListItem';

export default {
    name: 'List',
    components: {
        ListItem,
    },
    data() {
        return {
            candidates: [
                {"id": 1, "firstName": "James", "lastName": "Coombs", "jobTitle": "Software Engeineer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 2, "firstName": "Frank", "lastName": "Dalton", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 3, "firstName": "Stephen", "lastName": "Kendall", "jobTitle": "Software Engeineer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 4, "firstName": "Christin", "lastName": "Badger", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 5, "firstName": "Kate", "lastName": "Anstey", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 6, "firstName": "Cyrill", "lastName": "Enfield", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 7, "firstName": "Alex", "lastName": "Manley", "jobTitle": "Software Engeineer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 8, "firstName": "John", "lastName": "Lewis", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 9, "firstName": "Brad", "lastName": "Hackney", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 10, "firstName": "Matthew", "lastName": "Marleigh", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 11, "firstName": "Fin", "lastName": "Chatham", "jobTitle": "Software Engeineer", "photo": require('@/assets/user-placeholder.jpg')},
                {"id": 12, "firstName": "Andrew", "lastName": "Kekw", "jobTitle": "Designer", "photo": require('@/assets/user-placeholder.jpg')},
            ]
        }
    },
    methods: {
        getPpl() {
            prompt(this.candidates);
        }
    },
    computed: {
        sortByName() {
            return this.candidates.map(person => person).sort((a, b) => a.firstName - b.firstName);
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



