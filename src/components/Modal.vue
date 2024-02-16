<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal">
          <slot></slot>
          <div>
            <slot name="link"></slot>
          </div>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        closeModal() {
            this.$emit('close');
        }
    }
}
</script>

<style lang="scss" scoped>
.backdrop {
    background-color: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    display: flex;
    align-items: center;
}

.modal {
    width: 400px;
    height: 300px;
    background-color: white;
    margin: 0 auto;
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    h2 {
        margin-bottom: 10px;
    }
}

</style>