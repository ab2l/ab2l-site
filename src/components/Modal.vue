<template>
  <div class="Modal" :class="style">
    <!--<div class="Modal__close" @click="close"></div>-->
    <div class="Modal__closeButton" @click="close">
      <svg viewBox="0 0 24 24" role="img" aria-label="Close" focusable="false" style="display: block; fill: rgb(118, 118, 118); height: 16px; width: 16px;"><path fill-rule="evenodd" d="M23.25 24a.744.744 0 0 1-.53-.22L12 13.062 1.28 23.782a.75.75 0 0 1-1.06-1.06L10.94 12 .22 1.28A.75.75 0 1 1 1.28.22L12 10.94 22.72.22a.749.749 0 1 1 1.06 1.06L13.062 12l10.72 10.72a.749.749 0 0 1-.53 1.28"></path></svg>
    </div>
    <div class="Modal__dialog">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isClose: false,
        isClosing: false,
      };
    },
    computed: {
      style() {
        return {
          'is-closing': this.isClosing,
        };
      },
    },
    methods: {
      close() {
        this.isClosing = true;
        window.setTimeout(() => {
          this.isClosing = false;
          this.$emit('close');
        }, 150);
      },
    },
  };
</script>

<style>
  .Modal {
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: 10;
    animation: fadeIn 0.15s ease-in-out forwards;
    background: rgba(255, 255, 255, 0.95);
  }
  .Modal__dialog {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    padding: 1rem;
  }

  .Modal.is-closing {
    animation: fadeOut 0.15s ease-in-out forwards;
  }
  .Modal__close {
    height: 100%;
    width: 100%;
    left: 0;
    top: 0;
    position: fixed;
    background: rgba(255, 255, 255, 0.9);
  }
  .Modal__closeButton {
    position: fixed;
    right: 0;
    top: 0;
    height: 4rem;
    width: 4rem;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }
  @keyframes fadeIn{
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
  @keyframes fadeOut{
    0% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }
</style>
