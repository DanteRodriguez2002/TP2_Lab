<script setup>
import NavBar from './components/NavBar.vue'
import ProfileCard from './components/ProfileCard.vue'
import SocialMedia from './components/SocialMedia.vue'
</script>
<template>
    <NavBar @addName="changeName" />
    <ProfileCard />
    <SocialMedia v-bind:name="username" />
</template>

<script>

export default {
    name: 'App',
    methods: {
        changeName(name) {
            this.username = name
        }
    },
    data: function () {
        return {
            username: ""
        }
    }
}
</script>

<style>
body {
    font-family: 'Montserrat', sans-serif;
    background-color: #F4F4F5;
}

.profile-photo {
    border-style: solid;
    border-radius: 50%;
    border-color: #3B82F6;
}

.card-rounded {
    border-radius: 30px;
    background-color: white;

}

.btn-follow {
    height: 100%;
}

.feed-img {
    width: 100%;
    border-radius: 40px;
    padding: 20px;
}

.btn-delete {
    margin-left: 5%;
}

.commet {
    margin-top: 2%;
}
</style>
