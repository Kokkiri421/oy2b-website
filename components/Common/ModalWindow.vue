<template>
  <!--  v-scroll-lock="show"-->
  <div
    id="myModal"
    class="modal"
    :class="{ show: show }"
    @mousedown="clickAnywhere"
  >
    <div class="modal-content-wrapper">
      <div class="modal-content">
        <slot></slot>
      </div>
      <div
        class="modal-close"
        :class="{ closeBg: closeBg }"
        @click="$emit('onClick')"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalWindow',

  methods: {
    clickAnywhere: function (e) {
      if (
        e.target.className === 'modal show' ||
        e.target.className === 'modal-content-wrapper'
      ) {
        this.$emit('onClick')
      }
    },
  },
  props: {
    show: {
      type: Boolean,
      required: true,
    },
    closeBg: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';

.modal {
  visibility: hidden;
  position: fixed;
  display: none;
  z-index: 20;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;

  background-color: rgba(0, 0, 0, 0.8);
  opacity: 0;
  transition: opacity 0.3s ease-out, visibility 0.3s ease-out;

  .modal-content-wrapper {
    z-index: 1;
    position: relative;
    text-align: left;
    margin: auto auto;
    overflow: hidden;
    padding: 50px;
    @include _700() {
      padding: 1em;
    }
  }

  .modal-content {
    background-color: #fefefe;
    margin: auto auto;
    overflow: hidden;
    border-radius: 6px;
    width: fit-content;
  }

  .modal-close {
    cursor: pointer;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 36px;
    right: 0;
    @include _700() {
      top: 1.5em;
      right: 1.5em;
      width: 2em;
      height: 2em;
    }

    &:hover {
      &:before {
        background-color: #d81428;
        transform: rotate(135deg);
      }

      &:after {
        background-color: #d81428;
        transform: rotate(45deg);
      }
    }

    &:before {
      content: '';
      position: absolute;
      top: 50%;
      right: 15%;
      width: 70%;
      height: 1px;
      background-color: #ddd;
      transform: rotate(45deg);
      transform-origin: 50% 50%;
      transition: transform 0.3s ease-out, background-color 0.3s ease-out;
    }

    &:after {
      content: '';
      position: absolute;
      top: 50%;
      right: 15%;
      width: 70%;
      height: 1px;
      background-color: #ddd;
      transform: rotate(-45deg);
      transform-origin: 50% 50%;
      transition: transform 0.3s ease-out, background-color 0.3s ease-out;
    }
  }
}

.show {
  display: flex;
  visibility: visible;
  opacity: 1;
  z-index: 199;
}

.closeBg {
  @include _700() {
    background-color: rgba(0, 0, 0, 0.6);
    border-radius: 30px;
  }
}
</style>
