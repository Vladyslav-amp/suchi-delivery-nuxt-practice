<template>
  <button class="back" @click="$router.back()"> <!--Listener which call method navigate back in browser history -->
    <IconAngleLeft class="back__icon" />
  </button>
</template>

<style lang="scss" scoped>
.back {
  display: flex;
  border: none;
  background-color: transparent;
  cursor: pointer;

  &__icon {
    height: 25px;
    width: 25px;
  }
}
</style>
