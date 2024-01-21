<script setup>
    const props = defineProps({
        guitarra: { /* Este Prop lo pasamos en App.vue de la siguiente manera v-bind:guitarra="guitarra" */
            type: Object,
            required: true
        }
    });
</script>

<template>        
    <div class="col-md-6 col-lg-4 my-4 row align-items-center"> <!-- guitarra es una variable que se está generando con el v-for -->
        <div class="col-4">
            <img class="img-fluid" :src="'/img/' + guitarra.imagen + '.jpg'" :alt="'imagen guitarra' + guitarra.nombre">
        </div>
        <div class="col-8">
            <h3 class="text-black fs-4 fw-bold text-uppercase">{{ guitarra.nombre }}</h3>
            <p>{{ guitarra.descripcion }}</p>
            <p class="fw-black text-primary fs-3">${{ guitarra.precio }}</p>
            <button 
                type="button"
                class="btn btn-dark w-100"
            >Agregar al Carrito</button>
        </div>
    </div>
</template>
