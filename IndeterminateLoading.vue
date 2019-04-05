<template>
  <span class="loader" :class="loaderClass"></span>
</template>

<script>
  // noinspection JSUnusedGlobalSymbols
  export default {
    name: "IndeterminateLoading",
    props: {
      isDarkMode: {
        type: Boolean,
        default: false
      }
    },
    computed: {
      loaderClass() {
        return this.isDarkMode ? "is--dark" : "";
      }
    }
  }
</script>

<style scoped lang="less">
  @import "~ampersanda-lessfiles/less/pseudos";
  @import "~ampersanda-lessfiles/less/pseudos";

  a.btn.btn--loading, button.btn.btn--loading, .loader {
    position: relative;
    color: transparent;
    user-select: none;

    .apply-after({ content: ''; -webkit-box-sizing: border-box; box-sizing: border-box; position: absolute; top: 50%; left: 50%; border-top: 2px solid; border-right: 2px solid transparent; border-radius: 50%; animation: spin 0.6s linear infinite; width: 1.4em; height: 1.4em; margin-top: -.7em; margin-left: -.7em; border-top-color: #fff; color: #fff; });

    &.is--dark {
      .apply-after({ border-top-color: #9816f4; color: #9816f4; });
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
