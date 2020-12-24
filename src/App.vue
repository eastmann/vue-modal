<template>
    <h1>{{ title }}</h1>
    <p>Welcome...</p>
    <teleport to="#modals" v-if="showModal">
        <Modal theme="sale" @close="toggleModal">
            <h1>Sign up for the Giveaway!</h1>
            <p>Grab your Ninja swag for a half price!</p>
            <template v-slot:links>
                <a href="#">Sign up</a>
                <a href="#">More info</a>
            </template>
        </Modal>
    </teleport>
    <teleport to="#modals" v-if="showModalTwo">
        <Modal @close="toggleModalTwo">
            <h1>Sign out</h1>
            <template v-slot:links>
                <a href="#">Sign out</a>
            </template>
        </Modal>
    </teleport>
    <button @click="toggleModal">Open Modal</button>
    <button @click="toggleModalTwo">Open Modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
    name: 'App',
    components: { Modal },
    data() {
        return {
            title: 'My First Vue App :)',
            showModal: false,
            showModalTwo: false
        }
    },
    methods: {
        toggleModal() {
            this.showModal = !this.showModal
        },
        toggleModalTwo() {
            this.showModalTwo = !this.showModalTwo
        }
    }
}
</script>

<style>
#app,
#modals {
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
