<!-- Las etiquetas <script>, <template> y <style> se les conoce como Single File Components (SFA)
      * scripts: Logica de desarrollo.
      * template: HTML que se mostrara en pantalla.
      * style: CSS/Sass que tendra el componente.
-->

<script setup>
  const hola = "Hola Mundo";
</script>

<template>
  <h1>{{ hola }}</h1>
</template>

<style scoped>
  h1 {
    text-transform: uppercase;
  }
</style>
