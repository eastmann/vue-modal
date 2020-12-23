<template>
    <h1>{{ title }}</h1>
    <p>Welcome...</p>
    <div v-if="showModal">
        <Modal theme="sale" @close="toggleModal">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
            <template v-slot:links>
                <a href="#">Sign up</a>
                <a href="#">More info</a>
            </template>
        </Modal>
    </div>
    <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
    name: 'App',
    components: { Modal },
    data() {
        return {
            title: 'My First Vue App :)',
            header: 'Sign up for the Giveaway!',
            text: 'Grab your Ninja swag for a half price!',
            showModal: false
        }
    },
    methods: {
        toggleModal() {
            this.showModal = !this.showModal
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

h1 {
    display: inline-block;
    border-bottom: 1px solid #ddd;
    padding-bottom: 10px;
}
</style>
