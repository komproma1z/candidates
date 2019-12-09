<template>
    <div class='list-item'>
        <div class="avatar-box"><img class='avatar-img' v-bind:src='candidate.photoUrl'></div>
        <span class="first-name">{{ candidate.firstName }}</span>
        <span class="surname">{{ candidate.lastName }}</span>
        <span class="job-title">{{ candidate.jobTitle }}</span>
        <v-flex class="mt-4 mb-4">
            <Modal v-bind:candidate='candidate'/>
        </v-flex>
    </div>
</template>

<script>
import Modal from './Modal';

export default {
    name: 'ListItem',
    props: ['candidate'],
    components: {
        Modal
    }
}
</script>

<style scoped>
    .list-item {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 3fr 2fr;
        grid-gap: 10px;
        align-items: center;
        width: 100%;
        padding: 10px 20px;
    }

    .avatar-box {
        width: 50px;
        height: 50px;
        border-radius: 50%;
    }

    .avatar-img {
        max-width: 100%;
        max-height: 100%;
        border-radius: 50%;
    }

    .btn {
        width: auto;
        height: 45px;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 17px;
        border-radius: 25px;
        font-size: 16px;
        background-color: #b5e5f5;
        cursor: pointer;
        transition: background-color 0.3s ease-in;
    }

    .btn:hover {
        background-color: #53ff9fc9;
    }
</style>



