<template>
  <span class="loader" :class="loaderClass" :style="`color: ${colorHash};`"></span>
</template>

<script>
  // noinspection JSUnusedGlobalSymbols
  export default {
    name: 'IndeterminateLoading',
    props: {
      isDarkMode: {
        type: Boolean,
        default: false,
      },
      colorHash: {
        type: String,
      },
    },
    computed: {
      loaderClass() {
        return this.isDarkMode ? 'is--dark' : '';
      },
    },
  };
</script>

<style lang="less">
  @import '~ampersanda-lessfiles/less/pseudos';

  // add integration to ampersanda-buttons
  .loader {
    position: relative;
    user-select: none;

    color: #fff;

    &::after {
      content: '';
      -webkit-box-sizing: border-box;
      box-sizing: border-box;
      position: absolute;
      top: 50%;
      left: 50%;
      border-top: 2px solid;
      border-right: 2px solid transparent;
      border-radius: 50%;
      animation: spin 0.6s linear infinite;
      width: 1.4em;
      height: 1.4em;
      margin-top: -.7em;
      margin-left: -.7em;
      border-top-color: inherit;
      color: inherit
    }

    &.is--dark {
      color: #9816f4;

      &::after {
        border-top-color: inherit;
        color: inherit
      }
    }
  }

  @keyframes spin {
    from {
      transform: rotateZ(0deg);
    }

    to {
      transform: rotateZ(360deg);
    }
  }

</style>
