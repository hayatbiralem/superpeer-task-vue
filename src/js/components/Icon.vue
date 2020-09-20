<template>
  <svg
    aria-hidden="true"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
  >
    <use :xlink:href="'#icon-' + icon"></use>
  </svg>
</template>

<script>
export default {
  name: "Icon",
  props: ["icon"]
};
</script>
