<template>
  <div class="row event-cover">

    </div>
</template>
<script>
export default {
  name: 'AboutView'
}
</script>
<style>
.event-cover {
  background-image: url('../assets/face2.png');
  transform: translate3d(0px, 0px, 0px);
    min-height: 40vh!important;
    background-color: #b2afab;
    background-position: 50%;
    background-size: cover;
    min-height: 130vh;
    max-height: 999px;
    overflow: hidden;
    position: relative;
    /* width: 100%; */
    z-index: 1;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>