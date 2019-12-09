<template>
    <v-dialog v-model='dialog' max-width="600px">
        <template v-slot:activator="{ on }">
            <v-btn color="cyan darken-1" dark v-on="on">View candidate</v-btn>
        </template>
        <v-card class="popup-card">
            <v-card-title class="card-title">
                <h2>Candidate profile</h2>
            </v-card-title>
            <div class="avatar-box"><img class='avatar-img' v-bind:src='candidate.photoUrl'></div>
            <v-card-text><strong>Candidate ID:</strong>  {{ candidate.id }}</v-card-text>
            <v-card-text><strong>Name:</strong> {{ candidate.firstName }}</v-card-text>
            <v-card-text><strong>Surame:</strong> {{ candidate.lastName }}</v-card-text>
            <v-card-text><strong>Occupation:</strong> {{ candidate.jobTitle }}</v-card-text>    
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="cyan darken-1" text @click="dialog = false">Close</v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>

<script>
export default {
    name: 'Modal',
    props: ['candidate'],
    data () {
        return {
            dialog: false,
        }
    }
}
</script>

<style scoped>
    .popup-card {
        padding-left: 50px;
    }

    .card-title {
        padding-left: 0 !important;
    }

    .avatar-box {
        width: 150px;
        height: 150px;
        margin: 15px 0;
        border-radius: 50%;
    }

    .avatar-img {
        max-width: 100%;
        max-height: 100%;
        border-radius: 50%;
    }

    .v-btn {
        border-radius: 20px;
    }

    .v-cart__text {
        font-size: 1rem;
    }
</style>