<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ 'sale': theme === 'sale'}">
            <slot>Default content</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'theme'
    ],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
    .modal {
        margin: 100px auto;
        padding: 20px;

        width: 400px;

        background: white;
        border-radius: 10px;
    }

    .backdrop {
        position: fixed;
        top: 0;

        width: 100%;
        height: 100%;

        background: rgba(0,0,0,0.5);
    }

    h1 {
        color: #03cfb4;

        border: none;
    }

    .modal.sale {
        background: crimson;
        color: white;
    }

    .modal .actions {
        margin: 30px 0 10px 0;

        text-align: center;
    }

    .modal .actions a {
        margin: 10px;
        padding: 8px;

        color: #333;
        text-decoration: none;

        border: 1px solid #eee;
        border-radius: 4px;
    }

    .modal.sale h1 {
        color: white;
    }

    .modal.sale .actions {
        color: white;
    }

    .modal.sale .actions a {
        color: white;
    }
</style>
