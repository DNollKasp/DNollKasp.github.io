<script setup>
const props = defineProps({
  show: Boolean
})
</script>

<template>
  <Transition name="modal">
    <div v-if="show" class="modal-mask">
      <div class="modal-container">
        <button
              class="modal-default-button"
              @click="$emit('close')"
            >X</button>
        <div class="modal-image">
          <slot name="image">default image</slot>
        </div>
        <div class="inner-modal-container">
          <div class="modal-header">
            <slot name="header">default header</slot>
          </div>

          <div class="modal-body">
            <slot name="body">default body</slot>
          </div>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style>



.modal-image {
  width: 100%;
}

.inner-modal-container {
  padding: 20px 30px;
}

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  transition: opacity 0.3s ease;
}

.modal-container {
  width: 350px;
  margin: auto;

  background-color: #3f3f3f;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  border-radius: 10px;
  position: relative;
}

.modal-header h3 {
  margin-top: 0;
  color: #ffa600;
  font-weight: 900;
  font-size: 1.5rem;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
  position: absolute;

  left: 315px;
  top: 10px;
  background-color: #3f3f3f;
  color: white;
  text-align: center;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter-from {
  opacity: 0;
}

.modal-leave-to {
  opacity: 0;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>