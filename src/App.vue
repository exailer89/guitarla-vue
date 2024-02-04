<script setup>
    import {ref, reactive, onMounted} from 'vue';
    import {db} from './data/guitarras';
    import Guitarra from './components/Guitarra.vue';
    import Header from './components/Header.vue';
    import Footer from './components/Footer.vue';

    // Creación de State
    const guitarras = ref([]);
    const carrito = ref([]);

    onMounted(() => {
        guitarras.value = db;
    });

    const agregarCarrito = (guitarra) => {
        const existeCarrito = carrito.value.findIndex(producto => producto.id === guitarra.id);

        if (existeCarrito >= 0) {
            carrito.value[existeCarrito].cantidad++;
        } else {
            guitarra.cantidad = 1;
            carrito.value.push(guitarra);
        }
    }

    const decrementarCantidad = () => {
        console.log('Menos...');
    }

    const incrementarCantida = () => {
        console.log('Mas...');
    }
</script>

<template>
    <Header 
        :carrito="carrito"
        @decrementar-cantidad="decrementarCantidad"
        @incrementar-cantidad="incrementarCantida"
    />

    <main class="container-xl mt-5">
        <h2 class="text-center">Nuestra Colección</h2>
        <div class="row mt-5">
            <Guitarra 
                v-for="guitarra in guitarras" 
                :guitarra="guitarra"
                @agregar-carrito="agregarCarrito"
            />
        </div>
    </main>

    <Footer />
</template>