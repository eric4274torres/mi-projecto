<template>
  <div class="fondo">
    <Tareas/>
  </div>

</template>

<script>
import Tareas from './components/Tareas.vue'

export default {
  name: 'App',
  components: {
    Tareas
  }
}
</script>

<style>

#app {
width: 50%;
height: 50%;

}
.fondo{
  height: 100%;

}
html{
    height: 100%;
}
body{
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.7));

}
</style>
