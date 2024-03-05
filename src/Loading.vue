<template>
  <div id="loading" class="loading">
    <div class="loader"></div>
  </div>
</template>

<style scoped lang="scss">
.loading {
  z-index: 9999;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  text-align: center;
  font-size: 0px;
  opacity: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  -webkit-transition: all 0.3s ease;
  -moz-transition: all 0.3s ease;
  -ms-transition: all 0.3s ease;
  -o-transition: all 0.3s ease;
  transition: all 0.3s ease;
  background-color: #FFDEE9;
  background-image: linear-gradient(0deg, #cbd7c7 0%, #cddbdb 100%);
}

/* HTML: <div class="loader"></div> */
.loader {
  width: 50px;
  aspect-ratio: 1;
  border-radius: 50%;
  padding: 3px;
  background:
    radial-gradient(farthest-side, #A9A9A9 95%, #0000) 50% 0/12px 12px no-repeat,
    radial-gradient(farthest-side, #0000 calc(100% - 5px), #c0c0c0 calc(100% - 4px)) content-box;
  animation: l6 2s infinite;
}

@keyframes l6 {
  to {
    transform: rotate(1turn)
  }
}

</style>