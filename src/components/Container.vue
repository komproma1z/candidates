<template>
    <div class="main-container">
        <h1 class="title">Candidates</h1>
        <div class='columns'>
            <span> </span>
            <span class="first-name">Name</span>
            <span class="surname">Surname</span>
            <span class="job-title">Occupation</span>
            <span> </span>
        </div>
        <List class="list-content" />
    </div>
</template>

<script>
import List from './List';

export default {
    name: 'Container',
    components: {
        List,
    }
}
</script>

<style scoped>
    .main-container {
        max-width: 800px;
        height: 95vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 20px 15px 15px 15px;
        flex: auto;
        align-self: center;
        border-radius: 5px 50px 5px 5px;
        box-shadow: -1px 1px 5px #c2c2c2;
    }

    .list-content {
        height: 80%;
    }

    .title {
        text-align: center;
        margin-bottom: 15px;
    }

    .columns {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 3fr 2fr;
        grid-gap: 10px;
        align-items: center;
        width: 100%;
        padding: 10px 20px;
        font-weight: bold;
        text-decoration: underline;
    }

    .v-application .title {
        font-size: 2rem !important;
    }
</style>
