<template>
  <div class="modal-window" :class="{ 'modal-window--show': showModal }">
    <div class="modal-window__wrapper">
      <h2 class="modal-window__title">Вы уверенны?</h2>
      <div class="modal-window__buttons-wrapper">
        <button @click="onOk" class="button button__edit modal-window__button">Да</button>
        <button @click="onCancel" class="button button__delete modal-window__button">Нет</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['showModal'],

  methods: {
    onOk() {
      this.$emit('on-ok', true);
    },

    onCancel() {
      this.$emit('on-cancel', false);
    },
  },
};
</script>

<style lang="scss" scoped>
.modal-window {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.2);
  width: 100vw;
  height: 100vh;

  &--show {
    display: block;
  }

  &__wrapper {
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 150px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: $second;
    border-radius: 8px;
  }

  &__title {
    width: 100%;
    text-align: center;
    line-height: 180%;
    color: $second;
    background-color: $prime;
    border-radius: 8px 8px 0 0;
  }

  &__buttons-wrapper {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-around;
  }

  &__button {
    width: 40%;
  }
}
</style>
